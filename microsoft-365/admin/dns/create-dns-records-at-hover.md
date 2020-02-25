---
title: Hover에서 Office 365용 DNS 레코드 만들기
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
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 Office 365에 대 한 가리키기의 기타 서비스에 대 한 DNS 레코드를 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 54ff58963dcd66f692507f1d778fb9a8d24f82fa
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42249271"
---
# <a name="create-dns-records-at-hover-for-office-365"></a><span data-ttu-id="eca02-103">Hover에서 Office 365용 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="eca02-103">Create DNS records at Hover for Office 365</span></span>

 <span data-ttu-id="eca02-104">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="eca02-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="eca02-105">DNS 호스팅 공급자로 Hover를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-105">If Hover is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
     
<span data-ttu-id="eca02-106">Hover에서 이러한 레코드를 추가하고 나면 도메인이 Office 365 서비스에서 작동하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-106">After you add these records at Hover, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="eca02-107">Office 365에서 웹 사이트의 웹 호스팅 및 DNS에 대한 자세한 내용은 [Office 365에서 공개 웹 사이트 사용](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eca02-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="eca02-p101">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eca02-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="eca02-111">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="eca02-111">Add a TXT record for verification</span></span>
<span data-ttu-id="eca02-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="eca02-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="eca02-p102">Office 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Office 365에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="eca02-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="eca02-117">아래 단계를 따르거나 [비디오를 시청하세요](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="eca02-117">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="eca02-p104">시작하려면 [이 링크](https://www.hover.com/domains)를 사용하여 Hover의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-p104">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![로그인](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="eca02-121">**도메인 관리**에서 편집 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-121">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![도메인 선택](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="eca02-123">**DNS** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-123">Select the **DNS** tab.</span></span> 
    
    ![DNS 탭을 선택 합니다.](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="eca02-125">**새로 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-125">Select **Add New**.</span></span>
    
    ![새로 추가를 선택 합니다.](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="eca02-127">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="eca02-127">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="eca02-128">Hostname(호스트 이름)</span><span class="sxs-lookup"><span data-stu-id="eca02-128">Hostname</span></span>  <br/> |<span data-ttu-id="eca02-129">레코드 종류</span><span class="sxs-lookup"><span data-stu-id="eca02-129">Record Type</span></span>  <br/> |<span data-ttu-id="eca02-130">Value(값)</span><span class="sxs-lookup"><span data-stu-id="eca02-130">Value</span></span>  <br/> |
    |@  <br/> |<span data-ttu-id="eca02-131">TXT</span><span class="sxs-lookup"><span data-stu-id="eca02-131">TXT</span></span>  <br/> |<span data-ttu-id="eca02-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="eca02-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="eca02-133">**참고:** 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-133">**Note:** This is an example.</span></span> <span data-ttu-id="eca02-134">여기에는 Office 365의 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-134">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="eca02-135">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="eca02-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![DNS 값을 입력 하거나 복사 하 여 붙여넣기](../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. <span data-ttu-id="eca02-137">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-137">Select **Save**.</span></span>
    
    ![저장을 선택](../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. <span data-ttu-id="eca02-139">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="eca02-140">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="eca02-140">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="eca02-141">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="eca02-141">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="eca02-142">관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="eca02-143">**도메인** 페이지에서 확인 하려는 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="eca02-144">**설정** 페이지에서 **설정 시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="eca02-145">**도메인 확인** 페이지에서 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="eca02-p106">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eca02-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="eca02-149">사용자 도메인의 전자 메일이 Office 365로 전송되도록 MX 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="eca02-149">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="eca02-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="eca02-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="eca02-151">아래 단계를 따르거나 [비디오를 시청하세요](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="eca02-151">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="eca02-p107">시작하려면 [이 링크](https://www.hover.com/domains)를 사용하여 Hover의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-p107">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![로그인](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="eca02-155">**도메인 관리**에서 편집 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-155">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![도메인 선택](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="eca02-157">**DNS** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-157">Select the **DNS** tab.</span></span> 
    
    ![DNS 탭을 선택 합니다.](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="eca02-159">**새로 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-159">Select **Add New**.</span></span>
    
    ![새로 추가를 선택 합니다.](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="eca02-161">새 레코드의 상자에서 **레코드 종류**에 **MX**를 선택한 후 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-161">In the boxes for the new record, select **MX** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="eca02-162">**Hostname(호스트 이름)**</span><span class="sxs-lookup"><span data-stu-id="eca02-162">**Hostname**</span></span>|<span data-ttu-id="eca02-163">**Record Type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="eca02-163">**Record Type**</span></span>|<span data-ttu-id="eca02-164">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="eca02-164">**Priority**</span></span>|<span data-ttu-id="eca02-165">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="eca02-165">**Hostname**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="eca02-166">MX</span><span class="sxs-lookup"><span data-stu-id="eca02-166">MX</span></span>  <br/> |<span data-ttu-id="eca02-167">개</span><span class="sxs-lookup"><span data-stu-id="eca02-167">0</span></span>  <br/> <span data-ttu-id="eca02-168">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eca02-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="eca02-169">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="eca02-169">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="eca02-170">**참고:** Office 365 계정에서 \* \<도메인\> 키\* 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-170">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="eca02-171">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="eca02-171">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![DNS 값을 입력 하거나 복사 하 여 붙여넣기](../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. <span data-ttu-id="eca02-173">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-173">Select **Save**.</span></span>
    
    ![저장을 선택](../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. <span data-ttu-id="eca02-175">다른 MX 레코드가 있으면 다음 2단계 절차를 사용하여 각 레코드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-175">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="eca02-176">먼저 제거 하려는 레코드를 두고 **삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-176">First, mousing over a record that you want to remove, select **Delete**.</span></span>
    
    ![마우스를 위로 가져가면 삭제를 선택 합니다.](../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    <span data-ttu-id="eca02-178">두 번째로, **예** 를 선택 하 여 삭제를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-178">Second, select **Yes** to confirm each deletion.</span></span> 
    
    ![삭제를 확인 하려면 예를 선택 합니다.](../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    <span data-ttu-id="eca02-180">이 절차의 앞부분에서 추가한 레코드를 제외한 모든 MX 레코드가 제거될 때까지 이 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-180">Repeat this process until you have deleted all MX records except for the one that you added earlier in this procedure.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="eca02-181">Office 365에 필요한 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="eca02-181">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="eca02-182"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="eca02-182"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="eca02-183">아래 단계를 따르거나 [비디오를 시청하세요](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="eca02-183">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="eca02-p109">시작하려면 [이 링크](https://www.hover.com/domains)를 사용하여 Hover의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-p109">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![로그인](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="eca02-187">**도메인 관리**에서 편집 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-187">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![도메인 선택](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="eca02-189">**DNS** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-189">Select the **DNS** tab.</span></span> 
    
    ![DNS 탭을 선택 합니다.](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="eca02-191">6개의 CNAME 레코드 중 첫 번째 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-191">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="eca02-192">**새로 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-192">Select **Add New**.</span></span>
    
    ![새로 추가를 선택 합니다.](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="eca02-194">새 레코드의 빈 상자에서 **레코드 종류**로 **CNAME**을 선택한 후 다음 표의 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-194">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="eca02-195">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="eca02-195">**Hostname**</span></span>|<span data-ttu-id="eca02-196">**Record Type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="eca02-196">**Record Type**</span></span>|<span data-ttu-id="eca02-197">**대상 호스트**</span><span class="sxs-lookup"><span data-stu-id="eca02-197">**Target Host**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="eca02-198">autodiscover</span><span class="sxs-lookup"><span data-stu-id="eca02-198">autodiscover</span></span>  <br/> |<span data-ttu-id="eca02-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="eca02-199">CNAME</span></span>  <br/> |<span data-ttu-id="eca02-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="eca02-200">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="eca02-201">sip</span><span class="sxs-lookup"><span data-stu-id="eca02-201">sip</span></span>  <br/> |<span data-ttu-id="eca02-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="eca02-202">CNAME</span></span>  <br/> |<span data-ttu-id="eca02-203">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="eca02-203">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="eca02-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="eca02-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="eca02-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="eca02-205">CNAME</span></span>  <br/> |<span data-ttu-id="eca02-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="eca02-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="eca02-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="eca02-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="eca02-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="eca02-208">CNAME</span></span>  <br/> |<span data-ttu-id="eca02-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="eca02-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="eca02-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="eca02-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="eca02-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="eca02-211">CNAME</span></span>  <br/> |<span data-ttu-id="eca02-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="eca02-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![DNS 값을 입력 하거나 복사 하 여 붙여넣기](../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. <span data-ttu-id="eca02-214">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-214">Select **Save**.</span></span>
    
    ![저장을 선택](../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. <span data-ttu-id="eca02-216">앞의 세 가지 단계와 표의 나머지 5개 행에 있는 값을 사용하여 나머지 5개의 CNAME 레코드를 각각 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-216">Using the preceding three steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="eca02-217">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="eca02-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="eca02-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="eca02-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="eca02-219">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="eca02-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="eca02-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="eca02-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="eca02-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="eca02-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="eca02-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="eca02-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="eca02-223">아래 단계를 따르거나 [비디오를 시청하세요](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="eca02-223">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="eca02-p111">시작하려면 [이 링크](https://www.hover.com/domains)를 사용하여 Hover의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-p111">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![로그인](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="eca02-227">**도메인 관리**에서 편집 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-227">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![도메인 선택](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="eca02-229">**DNS** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-229">Select the **DNS** tab.</span></span> 
    
    ![DNS 탭을 선택 합니다.](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="eca02-231">**새로 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-231">Select **Add New**.</span></span>
    
    ![새로 추가를 선택 합니다.](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="eca02-233">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="eca02-233">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="eca02-234">**Hostname(호스트 이름)**</span><span class="sxs-lookup"><span data-stu-id="eca02-234">**Hostname**</span></span>|<span data-ttu-id="eca02-235">**Record Type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="eca02-235">**Record Type**</span></span>|<span data-ttu-id="eca02-236">**값**</span><span class="sxs-lookup"><span data-stu-id="eca02-236">**Value**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="eca02-237">TXT</span><span class="sxs-lookup"><span data-stu-id="eca02-237">TXT</span></span>  <br/> |<span data-ttu-id="eca02-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="eca02-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="eca02-239">**참고:** 모든 공백이 올바르게 유지 되도록이 항목을 복사 하 여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![DNS 값을 입력 하거나 복사 하 여 붙여넣기](../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. <span data-ttu-id="eca02-241">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-241">Select **Save**.</span></span>
    
    ![저장을 선택](../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="eca02-243">Office 365에 필요한 2개의 SRV 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="eca02-243">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="eca02-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="eca02-244"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="eca02-245">아래 단계를 따르거나 [비디오를 시청하세요](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="eca02-245">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="eca02-p112">시작하려면 [이 링크](https://www.hover.com/domains)를 사용하여 Hover의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-p112">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![로그인](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="eca02-249">**도메인 관리**에서 편집 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-249">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![도메인 선택](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="eca02-251">**DNS** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-251">Select the **DNS** tab.</span></span> 
    
    ![DNS 탭을 선택 합니다.](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="eca02-253">처음 2개의 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-253">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="eca02-254">**새로 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-254">Select **Add New**.</span></span>
    
    ![새로 추가를 선택 합니다.](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="eca02-256">새 레코드의 빈 상자에서 **레코드 종류**로 **SRV**를 선택한 후 다음 표의 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-256">In the empty boxes for the new record, select **SRV** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="eca02-257">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="eca02-257">**Hostname**</span></span>|<span data-ttu-id="eca02-258">**Record Type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="eca02-258">**Record Type**</span></span>|<span data-ttu-id="eca02-259">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="eca02-259">**Priority**</span></span>|<span data-ttu-id="eca02-260">**가중치**</span><span class="sxs-lookup"><span data-stu-id="eca02-260">**Weight**</span></span>|<span data-ttu-id="eca02-261">**포트**</span><span class="sxs-lookup"><span data-stu-id="eca02-261">**Port**</span></span>|<span data-ttu-id="eca02-262">**대상**</span><span class="sxs-lookup"><span data-stu-id="eca02-262">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="eca02-263">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="eca02-263">_sip._tls</span></span>  <br/> |<span data-ttu-id="eca02-264">SRV</span><span class="sxs-lookup"><span data-stu-id="eca02-264">SRV</span></span>  <br/> |<span data-ttu-id="eca02-265">100</span><span class="sxs-lookup"><span data-stu-id="eca02-265">100</span></span>  <br/> |<span data-ttu-id="eca02-266">개</span><span class="sxs-lookup"><span data-stu-id="eca02-266">1</span></span>  <br/> |<span data-ttu-id="eca02-267">443</span><span class="sxs-lookup"><span data-stu-id="eca02-267">443</span></span>  <br/> |<span data-ttu-id="eca02-268">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="eca02-268">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="eca02-269">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="eca02-269">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="eca02-270">SRV</span><span class="sxs-lookup"><span data-stu-id="eca02-270">SRV</span></span>  <br/> |<span data-ttu-id="eca02-271">100</span><span class="sxs-lookup"><span data-stu-id="eca02-271">100</span></span>  <br/> |<span data-ttu-id="eca02-272">개</span><span class="sxs-lookup"><span data-stu-id="eca02-272">1</span></span>  <br/> |<span data-ttu-id="eca02-273">5061</span><span class="sxs-lookup"><span data-stu-id="eca02-273">5061</span></span>  <br/> |<span data-ttu-id="eca02-274">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="eca02-274">sipfed.online.lync.com</span></span>  <br/> |
   
    ![DNS 값을 입력 하거나 복사 하 여 붙여넣기](../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. <span data-ttu-id="eca02-276">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-276">Select **Save**.</span></span>
    
    ![저장을 선택](../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. <span data-ttu-id="eca02-278">앞의 세 가지 단계와 표의 두 번째 행에 있는 값을 사용하여 나머지 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="eca02-278">Using the preceding three steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="eca02-p113">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eca02-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
