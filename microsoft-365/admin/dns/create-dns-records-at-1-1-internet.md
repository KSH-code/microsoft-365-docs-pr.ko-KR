---
title: 1&에 DNS 레코드 만들기 Office 365의 경우 1gb OS
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
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대 한 DNS 레코드를 설정 하는 방법에 대해 설명 합니다 (예를 들어, Office 365에 대 한&1gb OS).
ms.openlocfilehash: e31c9d9d08e29156ff6197c030de6b0f4169b5f4
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211874"
---
# <a name="create-dns-records-at-11-ionos-for-office-365"></a><span data-ttu-id="cf7e9-103">1&에 DNS 레코드 만들기 Office 365의 경우 1gb OS</span><span class="sxs-lookup"><span data-stu-id="cf7e9-103">Create DNS records at 1&1 IONOS for Office 365</span></span>

 <span data-ttu-id="cf7e9-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="cf7e9-105">1&, 1gb OS는 도메인이 MX 레코드와 최상위 자동 검색 CNAME 레코드를 모두 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-105">Note that 1&1 IONOS doesn't allow a domain to have both an MX record and a top-level Autodiscover CNAME record.</span></span> <span data-ttu-id="cf7e9-106">이를 통해 Office 365에 대해 Exchange Online을 구성 하는 방법이 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-106">This limits the ways in which you can configure Exchange Online for Office 365.</span></span> <span data-ttu-id="cf7e9-107">해결 방법은 있지만 1&1gb OS에서 하위 도메인을 만든 경험이 이미 있는 경우에 **만** 이 방법을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-107">There is a workaround, but we recommend employing it **only** if you already have experience with creating subdomains at 1&1 IONOS.</span></span> <span data-ttu-id="cf7e9-108">>이 [서비스 제한은](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) 1&1gb os에서 자체 OFFICE 365 DNS 레코드를 관리 하도록 선택 하는 경우에는이 문서의 단계에 따라 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 등에 대 한 DNS 레코드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-108">> If despite this [service limitation](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) you choose to manage your own Office 365 DNS records at 1&1 IONOS, follow the steps in this article to verify your domain and to set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="cf7e9-109">1&, 1gb OS에서 이러한 레코드를 추가 하 고 나면 도메인이 Office 365 서비스에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-109">After you add these records at 1&1 IONOS, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="cf7e9-110">Office 365에서 웹 사이트의 웹 호스팅 및 DNS에 대한 자세한 내용은 [Office 365에서 공개 웹 사이트 사용](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-110">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="cf7e9-111">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-111">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="cf7e9-112">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-112">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="cf7e9-113">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [Office 365에서 도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-113">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="cf7e9-114">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="cf7e9-114">Add a TXT record for verification</span></span>

<span data-ttu-id="cf7e9-p103">Office 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Office 365에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cf7e9-p104">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="cf7e9-119">아래 단계를 따르거나 [비디오를 시청하세요(0:42에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="cf7e9-119">Follow the steps below or [watch the video (start at 0:42)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="cf7e9-120">시작 하려면 [이 링크](https://my.1and1.com/)를 사용 하 여 1&1gb os의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-120">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="cf7e9-121">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-121">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="cf7e9-122">**도메인 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-122">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="cf7e9-123">**Domain Center (도메인 센터** ) 페이지에서 업데이트 하려는 도메인을 찾은 다음 해당 도메인에 대 한 **패널** ( **v**) 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-123">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="cf7e9-124">**도메인 설정** 영역에서 **DNS 설정 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-124">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="cf7e9-125">**TXT 및 SRV 레코드** 섹션에서 **레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-125">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="cf7e9-126">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-126">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="cf7e9-127">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-127">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="cf7e9-128">**종류**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-128">**Type**</span></span> <br/> |<span data-ttu-id="cf7e9-129">**Prefix(접두사)**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-129">**Prefix**</span></span> <br/> |<span data-ttu-id="cf7e9-130">**Name Value(이름 값)**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-130">**Name Value**</span></span> <br/> |
    |<span data-ttu-id="cf7e9-131">TXT</span><span class="sxs-lookup"><span data-stu-id="cf7e9-131">TXT</span></span>  <br/> |<span data-ttu-id="cf7e9-132">(이 필드를 비워 둠)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-132">(Leave this field blank)</span></span>  <br/> |<span data-ttu-id="cf7e9-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="cf7e9-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="cf7e9-134">참고:이는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-134">NOTE: This is an example.</span></span> <span data-ttu-id="cf7e9-135">여기에는 Office 365의 표에 있는 특정 **보낼 대상 또는 지점** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-135">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="cf7e9-136">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="cf7e9-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="cf7e9-137">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-137">Select **Save**.</span></span>
    
8. <span data-ttu-id="cf7e9-138">**저장** 을 다시 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-138">Select **Save** again.</span></span> 
    
9. <span data-ttu-id="cf7e9-139">**DNS 설정 편집** 대화 상자에서 **예**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-139">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="cf7e9-140">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="cf7e9-141">이제 도메인 등록 기관에 레코드가 추가되었습니다. Office 365로 돌아가서 Office 365에 레코드를 찾을 것을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="cf7e9-142">Office 365에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="cf7e9-143">I관리 센터에서 \*\* 설정 \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="cf7e9-144">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="cf7e9-145">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-145">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="cf7e9-146">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-146">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cf7e9-147">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-147">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="cf7e9-148">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-148">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="cf7e9-149">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [Office 365에서 도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-149">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="cf7e9-150">사용자 도메인의 전자 메일이 Office 365로 전송되도록 MX 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="cf7e9-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="cf7e9-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="cf7e9-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="cf7e9-152">아래 단계를 따르거나 [비디오를 시청하세요(3:22에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="cf7e9-152">Follow the steps below or [watch the video (start at 3:22)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="cf7e9-153">1und1.de에 등록 한 경우 [여기에 로그인](https://go.microsoft.com/fwlink/?linkid=859152)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-153">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="cf7e9-154">시작 하려면 [이 링크](https://my.1and1.com/)를 사용 하 여 1&1gb os의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-154">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="cf7e9-155">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-155">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="cf7e9-156">**도메인 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-156">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="cf7e9-157">**Domain Center (도메인 센터** ) 페이지에서 업데이트 하려는 도메인을 찾은 다음 해당 도메인에 대 한 **패널** ( **v**) 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-157">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="cf7e9-158">**도메인 설정** 영역에서 **DNS 설정 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-158">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="cf7e9-159">In the **MX Records** section, in the \*\* Mail Exchanger (MX Record) \*\* area, select **Other mail server**.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-159">In the **MX Records** section, in the \*\* Mail Exchanger (MX Record) \*\* area, select **Other mail server**.</span></span><br/><span data-ttu-id="cf7e9-160">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-160">(You may have to scroll down.)</span></span><br/><span data-ttu-id="cf7e9-161">![1&amp;1-BP-구성-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-161">![1&amp;1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span></span> <br/>
  
6. <span data-ttu-id="cf7e9-162">MX 레코드가 이미 나열되어 있으면 레코드를 선택한 다음 키보드의 **Delete** 키를 눌러 하나씩 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-162">If there are any MX records already listed, delete each of them by selecting the record and then pressing the **Delete** key on your keyboard.</span></span><br/><span data-ttu-id="cf7e9-163">(MX 레코드가 나열되어 있지 않으면 다음 단계를 진행합니다.)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-163">(If there are no MX records already listed, continue to the next step.)</span></span><br/><span data-ttu-id="cf7e9-164">![1&amp;1-BP-구성-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-164">![1&amp;1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span></span><br/>
  
7. <span data-ttu-id="cf7e9-165">**MX 1** 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-165">In the boxes for the **MX 1** record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="cf7e9-166">**MX 1**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-166">**MX 1**</span></span>|<span data-ttu-id="cf7e9-167">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-167">**Priority**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="cf7e9-168">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="cf7e9-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <span data-ttu-id="cf7e9-169">NOTE: Office 365 \<계정에서 도메인\> 키를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-169">NOTE: Get your \<domain-key\> from your Office 365 account.</span></span> [<span data-ttu-id="cf7e9-170">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="cf7e9-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="cf7e9-171">10 </span><span class="sxs-lookup"><span data-stu-id="cf7e9-171">10</span></span>  <br/> <span data-ttu-id="cf7e9-172">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-172">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | 
    
    ![1, 1-2 및 3 구성](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. <span data-ttu-id="cf7e9-174">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-174">Select **Save**.</span></span><br/><span data-ttu-id="cf7e9-175">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-175">(You may have to scroll down.)</span></span><br/><span data-ttu-id="cf7e9-176">![1&amp;1-BP-구성-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-176">![1&amp;1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span></span>
  
9. <span data-ttu-id="cf7e9-177">**DNS 설정 편집** 대화 상자에서 **예**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-177">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="cf7e9-178">![DNS 설정 편집 대화 상자에서 예 선택](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-178">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="cf7e9-179">Office 365에 필요한 6개의 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="cf7e9-179">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="cf7e9-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="cf7e9-180"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="cf7e9-181">1&,. | s e r o r 2는 Office 365 전자 메일 서비스에 필요한 CNAME 레코드와 함께 MX 레코드를 사용할 수 있도록 해결 방법이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-181">1&1 IONOS requires a workaround so that you can use an MX record together with the CNAME records that are required for Office 365 email services.</span></span> <span data-ttu-id="cf7e9-182">이 해결 방법을 사용 하려면 1&, 1gb OS의 하위 도메인 집합을 만들고이를 CNAME 레코드에 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-182">This workaround requires you to create a set of subdomains at 1&1 IONOS, and to assign them to CNAME records.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="cf7e9-183">이 절차를 시작하기 전에 두 개 이상의 하위 도메인을 사용할 수 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-183">Make sure that you have at least two available subdomains before starting this procedure.</span></span> <span data-ttu-id="cf7e9-184">1&1gb OS에서 하위 도메인을 만든 경험이 이미 있는 경우에만이 솔루션을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-184">We recommend this solution only if you already have experience with creating subdomains at 1&1 IONOS.</span></span> 
  
### <a name="basic-cname-records"></a><span data-ttu-id="cf7e9-185">기본 CNAME 레코드</span><span class="sxs-lookup"><span data-stu-id="cf7e9-185">Basic CNAME records</span></span>

<span data-ttu-id="cf7e9-186">아래 단계를 따르거나 [비디오를 시청하세요(3:57에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="cf7e9-186">Follow the steps below or [watch the video (start at 3:57)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="cf7e9-187">1und1.de에 등록 한 경우 [여기에 로그인](https://go.microsoft.com/fwlink/?linkid=859152)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-187">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="cf7e9-188">시작 하려면 [이 링크](https://my.1and1.com/)를 사용 하 여 1&1gb os의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-188">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="cf7e9-189">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-189">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="cf7e9-190">**도메인 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-190">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="cf7e9-191">**Domain Center (도메인 센터** ) 페이지에서 업데이트 하려는 도메인을 찾은 다음 하위 **도메인 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-191">On the **Domain Center** page, find the domain that you want to update, and then select **Manage Subdomains**.</span></span><br/><span data-ttu-id="cf7e9-192">![1&amp;1-BP-구성-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-192">![1&amp;1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span></span> <br/><span data-ttu-id="cf7e9-193">두 개의 하위 도메인을 만들고 각 도메인에 대한 **별칭** 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-193">Now you'll create two subdomains and set an **Alias** value for each.</span></span><br/><span data-ttu-id="cf7e9-194">1&, 1gb OS는 최상위 CNAME 레코드를 하나만 지원 하기 때문에 필요 하지만 Office 365에는 여러 CNAME 레코드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-194">(This is required because 1&1 IONOS supports only one top-level CNAME record, but Office 365 requires several CNAME records.)</span></span><br/><span data-ttu-id="cf7e9-195">먼저 자동 검색 하위 도메인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-195">First, you'll create the Autodiscover subdomain.</span></span>
    
4. <span data-ttu-id="cf7e9-196">하위 **도메인 개요** 섹션에서 하위 **도메인 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-196">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
    ![1&amp;1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. <span data-ttu-id="cf7e9-p113">새 하위 도메인에 대한 **하위 도메인 만들기** 상자에 다음 표의 **하위 도메인 만들기** 값만 입력하거나 복사하여 붙여넣습니다. (이후 단계에서 **별칭** 값을 추가합니다.)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-p113">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span>

    |<span data-ttu-id="cf7e9-200">**하위 도메인 만들기**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-200">**Create Subdomain**</span></span>|<span data-ttu-id="cf7e9-201">**별칭**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-201">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="cf7e9-202">autodiscover</span><span class="sxs-lookup"><span data-stu-id="cf7e9-202">autodiscover</span></span>  <br/> |<span data-ttu-id="cf7e9-203">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="cf7e9-203">autodiscover.outlook.com</span></span>   | 

    ![1&amp;1-BP-구성-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. <span data-ttu-id="cf7e9-205">하위 **도메인 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-205">Select **Create Subdomain**.</span></span><br/><span data-ttu-id="cf7e9-206">![1&amp;1-BP-구성-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-206">![1&amp;1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span></span>
  
7. <span data-ttu-id="cf7e9-207">하위 **도메인 개요** 섹션에서 방금 만든 **자동 검색** 하위 도메인을 찾은 다음 해당 하위 도메인에 대 한 **패널 (v)** 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-207">In the **Subdomain Overview** section, locate the **autodiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="cf7e9-208">![1&amp;1-BP-구성-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-208">![1&amp;1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span></span>
  
8. <span data-ttu-id="cf7e9-209">하위 **도메인 설정** 영역에서 **DNS 설정 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-209">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span> <br/><span data-ttu-id="cf7e9-210">![1&amp;1-BP-구성-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-210">![1&amp;1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span></span>
  
9. <span data-ttu-id="cf7e9-211">**A/AAAA 레코드 (Ip 주소)** 섹션의 **Ip 주소 (레코드)** 영역에서 **CNAME**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-211">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span><br/><span data-ttu-id="cf7e9-212">![1&amp;1-BP-구성-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-212">![1&amp;1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span></span>
  
10. <span data-ttu-id="cf7e9-213">**별칭:** 상자에서 다음 표의 **별칭** 값만 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-213">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span><br/> 
    
    |<span data-ttu-id="cf7e9-214">**하위 도메인 만들기**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-214">**Create Subdomain**</span></span>|<span data-ttu-id="cf7e9-215">**별칭**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-215">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="cf7e9-216">autodiscover</span><span class="sxs-lookup"><span data-stu-id="cf7e9-216">autodiscover</span></span>  <br/> |<span data-ttu-id="cf7e9-217">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="cf7e9-217">autodiscover.outlook.com</span></span>   |

    ![1&amp;1-BP-구성-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. <span data-ttu-id="cf7e9-219">고지 사항을 **알고 있음**에 대한 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-219">Select the check box for the **I am aware** disclaimer.</span></span><br/><span data-ttu-id="cf7e9-220">![1&amp;1-BP-구성-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-220">![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span></span>
  
12. <span data-ttu-id="cf7e9-221">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-221">Select **Save**.</span></span><br/><span data-ttu-id="cf7e9-222">![1&amp;1-BP-구성-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-222">![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span></span>
  
  
### <a name="additional-cname-records"></a><span data-ttu-id="cf7e9-223">추가 CNAME 레코드</span><span class="sxs-lookup"><span data-stu-id="cf7e9-223">Additional CNAME records</span></span>

<span data-ttu-id="cf7e9-p114">다음 절차에서 만든 추가 CNAME 레코드가 비즈니스용 Skype Online 서비스를 활성화합니다. 이미 만든 2개의 CNAME 레코드를 만들 때와 동일한 단계를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-p114">The additional CNAME records created in the following procedure enable Skype for Business Online services. You will employ the same steps that you used to create the two CNAME records you have already created.</span></span>
  
1. <span data-ttu-id="cf7e9-226">세 번째 하위 도메인(Lyncdiscover)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-226">Create the third subdomain (Lyncdiscover).</span></span><br/><span data-ttu-id="cf7e9-227">하위 **도메인 개요** 섹션에서 하위 **도메인 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-227">On the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
2. <span data-ttu-id="cf7e9-p115">새 하위 도메인에 대한 **하위 도메인 만들기** 상자에 다음 표의 **하위 도메인 만들기** 값만 입력하거나 복사하여 붙여넣습니다. (이후 단계에서 **별칭** 값을 추가합니다.)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-p115">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span><br/> 
    
    |<span data-ttu-id="cf7e9-230">**하위 도메인 만들기**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-230">**Create Subdomain**</span></span>|<span data-ttu-id="cf7e9-231">**별칭**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-231">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="cf7e9-232">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="cf7e9-232">lyncdiscover</span></span>   |<span data-ttu-id="cf7e9-233">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cf7e9-233">webdir.online.lync.com</span></span>  |
   
3. <span data-ttu-id="cf7e9-234">하위 **도메인 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-234">Select **Create Subdomain**.</span></span>
    
4. <span data-ttu-id="cf7e9-235">**도메인 센터** 페이지에서 하위 도메인 **관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-235">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
5. <span data-ttu-id="cf7e9-236">하위 **도메인 개요** 섹션에서 방금 만든 **lyncdiscover** 하위 도메인을 찾은 다음 해당 하위 도메인에 대 한 **패널 (v)** 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-236">In the **Subdomain Overview** section, find the **lyncdiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="cf7e9-237">하위 **도메인 설정** 영역에서 **DNS 설정 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-237">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
6. <span data-ttu-id="cf7e9-238">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-238">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span></span>
    
7. <span data-ttu-id="cf7e9-239">**별칭:** 상자에서 다음 표의 **별칭** 값만 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-239">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> <br/>
    
    |<span data-ttu-id="cf7e9-240">**하위 도메인 만들기**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-240">**Create Subdomain**</span></span>|<span data-ttu-id="cf7e9-241">**별칭**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-241">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="cf7e9-242">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="cf7e9-242">lyncdiscover</span></span>  <br/> |<span data-ttu-id="cf7e9-243">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cf7e9-243">webdir.online.lync.com</span></span>  <br/> |
   
8. <span data-ttu-id="cf7e9-244">**알고** 있는 고 지 사항에 대 한 확인란을 선택 하 고 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-244">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
9. <span data-ttu-id="cf7e9-245">**DNS 설정 편집** 대화 상자에서 **예**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-245">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="cf7e9-246">네 번째 하위 도메인(SIP)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-246">Create the fourth subdomain (SIP):</span></span> <br/><span data-ttu-id="cf7e9-247">하위 **도메인 개요** 섹션에서 하위 **도메인 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-247">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
11. <span data-ttu-id="cf7e9-p116">새 하위 도메인에 대한 **하위 도메인 만들기** 상자에 다음 표의 **하위 도메인 만들기** 값만 입력하거나 복사하여 붙여넣습니다. (이후 단계에서 **별칭** 값을 추가합니다.)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-p116">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.) </span></span><br/>
    
    |<span data-ttu-id="cf7e9-250">**하위 도메인 만들기**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-250">**Create Subdomain**</span></span>|<span data-ttu-id="cf7e9-251">**별칭**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-251">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="cf7e9-252">sip</span><span class="sxs-lookup"><span data-stu-id="cf7e9-252">sip</span></span>  <br/> |<span data-ttu-id="cf7e9-253">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cf7e9-253">sipdir.online.lync.com</span></span>  <br/> |
   
12. <span data-ttu-id="cf7e9-254">하위 **도메인 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-254">Select **Create Subdomain**.</span></span>
    
13. <span data-ttu-id="cf7e9-255">**도메인 센터** 페이지에서 하위 도메인 **관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-255">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
14. <span data-ttu-id="cf7e9-256">하위 **도메인 개요** 섹션에서 방금 만든 **sip** 하위 도메인을 찾은 다음 해당 하위 도메인에 대 한 **패널 (v)** 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-256">In the **Subdomain Overview** section, find the **sip** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="cf7e9-257">하위 **도메인 설정** 영역에서 **DNS 설정 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-257">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
15. <span data-ttu-id="cf7e9-258">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-258">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span></span>
    
16. <span data-ttu-id="cf7e9-259">**별칭:** 상자에서 다음 표의 **별칭** 값만 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-259">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> 
    
    |<span data-ttu-id="cf7e9-260">**하위 도메인 만들기**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-260">**Create Subdomain**</span></span>|<span data-ttu-id="cf7e9-261">**별칭**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-261">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="cf7e9-262">sip</span><span class="sxs-lookup"><span data-stu-id="cf7e9-262">sip</span></span>  <br/> |<span data-ttu-id="cf7e9-263">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cf7e9-263">sipdir.online.lync.com</span></span>  <br/> |
   
17. <span data-ttu-id="cf7e9-264">**알고** 있는 고 지 사항에 대 한 확인란을 선택 하 고 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-264">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
18. <span data-ttu-id="cf7e9-265">**DNS 설정 편집** 대화 상자에서 **예**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-265">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
### <a name="cname-records-needed-for-mdm"></a><span data-ttu-id="cf7e9-266">MDM에 필요한 CNAME 레코드</span><span class="sxs-lookup"><span data-stu-id="cf7e9-266">CNAME records needed for MDM</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf7e9-267">다른 4개의 CNAME 레코드를 만드는 데 사용한 절차를 따르되 다음 표의 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-267">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> 
  
|<span data-ttu-id="cf7e9-268">**하위 도메인 만들기**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-268">**Create Subdomain**</span></span>|<span data-ttu-id="cf7e9-269">**별칭**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-269">**Alias**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cf7e9-270">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="cf7e9-270">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="cf7e9-271">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="cf7e9-271">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="cf7e9-272">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="cf7e9-272">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="cf7e9-273">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cf7e9-273">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="cf7e9-274">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="cf7e9-274">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf7e9-275">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-275">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="cf7e9-276">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-276">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="cf7e9-277">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-277">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="cf7e9-278">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-278">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="cf7e9-279">예제가 필요하세요?</span><span class="sxs-lookup"><span data-stu-id="cf7e9-279">Need examples?</span></span> <span data-ttu-id="cf7e9-280">[Office 365에 대한 외부 Domain Name System 레코드](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-280">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="cf7e9-281">SPF 레코드의 유효성을 검사 하기 위해 이러한[spf 유효성 검사 도구](../setup/domains-faq.md)중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-281">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
<span data-ttu-id="cf7e9-282">아래 단계를 따르거나 [비디오를 시청하세요(5:09에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="cf7e9-282">Follow the steps below or [watch the video (start at 5:09)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="cf7e9-283">1und1.de에 등록 한 경우 [여기에 로그인](https://go.microsoft.com/fwlink/?linkid=859152)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-283">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="cf7e9-284">시작 하려면 [이 링크](https://my.1and1.com/)를 사용 하 여 1&1gb os의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-284">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="cf7e9-285">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-285">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="cf7e9-286">**도메인 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-286">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="cf7e9-287">**Domain Center (도메인 센터** ) 페이지에서 업데이트 하려는 도메인을 찾은 다음 해당 도메인에 대 한 **패널** (**v**) 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-287">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** (**v**) control for that domain.</span></span>
    
4. <span data-ttu-id="cf7e9-288">**도메인 설정** 영역에서 **DNS 설정 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-288">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="cf7e9-289">**TXT 및 SRV 레코드** 섹션에서 **레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-289">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="cf7e9-290">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-290">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="cf7e9-291">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-291">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> <br/><span data-ttu-id="cf7e9-292">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-292">(Choose the **Type** value from the drop-down list.)</span></span> <br/>
    
    |<span data-ttu-id="cf7e9-293">**종류**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-293">**Type**</span></span>|<span data-ttu-id="cf7e9-294">**Prefix(접두사)**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-294">**Prefix**</span></span>|<span data-ttu-id="cf7e9-295">**Name Value(이름 값)**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-295">**Name Value**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="cf7e9-296">TXT</span><span class="sxs-lookup"><span data-stu-id="cf7e9-296">TXT</span></span>  <br/> |<span data-ttu-id="cf7e9-297">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-297">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="cf7e9-298">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="cf7e9-298">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="cf7e9-299">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-299">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           | 
    
    ![TXT 레코드](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. <span data-ttu-id="cf7e9-301">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-301">Select **Save**.</span></span><br/><span data-ttu-id="cf7e9-302">![레코드 추가](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-302">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span></span>
  
8. <span data-ttu-id="cf7e9-303">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-303">Select **Save**.</span></span><br/><span data-ttu-id="cf7e9-304">![레코드 저장](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-304">![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span></span>
  
9. <span data-ttu-id="cf7e9-305">**DNS 설정 편집** 대화 상자에서 **예**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-305">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="cf7e9-306">![DNS 설정 편집 대화 상자에서 예 선택](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-306">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="cf7e9-307">Office 365에 필요한 2개의 SRV 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="cf7e9-307">Add the two SRV records that are required for Office 365</span></span>

<span data-ttu-id="cf7e9-308">아래 단계를 따르거나 [비디오를 시청하세요(5:51에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="cf7e9-308">Follow the steps below or [watch the video (start at 5:51)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="cf7e9-309">1und1.de에 등록 한 경우 [여기에 로그인](https://go.microsoft.com/fwlink/?linkid=859152)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-309">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="cf7e9-310">시작 하려면 [이 링크](https://my.1and1.com/)를 사용 하 여 1&1gb os의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-310">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="cf7e9-311">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-311">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="cf7e9-312">**도메인 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-312">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="cf7e9-313">**Domain Center (도메인 센터** ) 페이지에서 업데이트 하려는 도메인을 찾은 다음 해당 도메인에 대 한 **패널** ( **v**) 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-313">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="cf7e9-314">**도메인 설정** 영역에서 **DNS 설정 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-314">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="cf7e9-315">**TXT 및 SRV 레코드** 섹션에서 **레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-315">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="cf7e9-316">처음 2개의 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-316">Add the first of the two SRV records.</span></span><br/><span data-ttu-id="cf7e9-317">**레코드 추가** 영역의 새 레코드용 상자에 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-317">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> <br/><span data-ttu-id="cf7e9-318">(드롭다운 목록에서 **Type (종류** ) 및 **TTL** 값을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-318">(Choose the **Type** and **TTL** values from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cf7e9-319">**유형**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-319">**Type**</span></span>|<span data-ttu-id="cf7e9-320">**서비스**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-320">**Service**</span></span>|<span data-ttu-id="cf7e9-321">**프로토콜**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-321">**Protocol**</span></span>|<span data-ttu-id="cf7e9-322">**이름**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-322">**Name**</span></span>|<span data-ttu-id="cf7e9-323">**호스트**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-323">**Host**</span></span>|<span data-ttu-id="cf7e9-324">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-324">**Priority**</span></span>|<span data-ttu-id="cf7e9-325">**Weight(가중치)**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-325">**Weight**</span></span>|<span data-ttu-id="cf7e9-326">**Port(포트)**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-326">**Port**</span></span>|<span data-ttu-id="cf7e9-327">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cf7e9-327">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cf7e9-328">SRV</span><span class="sxs-lookup"><span data-stu-id="cf7e9-328">SRV</span></span>  <br/> |<span data-ttu-id="cf7e9-329">sip</span><span class="sxs-lookup"><span data-stu-id="cf7e9-329">sip</span></span>  <br/> |<span data-ttu-id="cf7e9-330">tls</span><span class="sxs-lookup"><span data-stu-id="cf7e9-330">tls</span></span>  <br/> |<span data-ttu-id="cf7e9-331">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-331">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="cf7e9-332">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cf7e9-332">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="cf7e9-333">100</span><span class="sxs-lookup"><span data-stu-id="cf7e9-333">100</span></span>  <br/> |<span data-ttu-id="cf7e9-334">1 </span><span class="sxs-lookup"><span data-stu-id="cf7e9-334">1</span></span>  <br/> |<span data-ttu-id="cf7e9-335">443</span><span class="sxs-lookup"><span data-stu-id="cf7e9-335">443</span></span>  <br/> |<span data-ttu-id="cf7e9-336">3600(1시간)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-336">3600 (1 h)</span></span>  <br/> |
    |<span data-ttu-id="cf7e9-337">SRV</span><span class="sxs-lookup"><span data-stu-id="cf7e9-337">SRV</span></span>  <br/> |<span data-ttu-id="cf7e9-338">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="cf7e9-338">sipfederationtls</span></span>  <br/> |<span data-ttu-id="cf7e9-339">tcp</span><span class="sxs-lookup"><span data-stu-id="cf7e9-339">tcp</span></span>  <br/> |<span data-ttu-id="cf7e9-340">(이 필드는 비워 둡니다.)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-340">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="cf7e9-341">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cf7e9-341">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="cf7e9-342">100</span><span class="sxs-lookup"><span data-stu-id="cf7e9-342">100</span></span>  <br/> |<span data-ttu-id="cf7e9-343">1 </span><span class="sxs-lookup"><span data-stu-id="cf7e9-343">1</span></span>  <br/> |<span data-ttu-id="cf7e9-344">5061</span><span class="sxs-lookup"><span data-stu-id="cf7e9-344">5061</span></span>  <br/> |<span data-ttu-id="cf7e9-345">3600(1시간)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-345">3600 (1 h)</span></span>  <br/> |  
    
    ![1&amp;1-BP-구성-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. <span data-ttu-id="cf7e9-347">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-347">Select **Save**.</span></span> <br/><span data-ttu-id="cf7e9-348">![1&amp;1-BP-구성-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-348">![1&amp;1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span></span>
  
8. <span data-ttu-id="cf7e9-349">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-349">Select **Save**.</span></span> <br/><span data-ttu-id="cf7e9-350">![1&amp;1-BP-구성-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-350">![1&amp;1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span></span>
  
9. <span data-ttu-id="cf7e9-351">**DNS 설정 편집** 대화 상자에서 **예**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-351">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span> <br/><span data-ttu-id="cf7e9-352">![DNS 설정 편집 대화 상자에서 예 선택](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="cf7e9-352">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
10. <span data-ttu-id="cf7e9-353">다른 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-353">Add the other SRV record.</span></span> <br/><span data-ttu-id="cf7e9-354">**TXT 및 SRV 레코드** 섹션에서 **레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-354">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="cf7e9-355">**레코드 추가** 영역에서 표에 있는 다른 행의 값을 사용 하 여 레코드를 만든 다음 다시 **추가**, **저장**및 **예** 를 선택 하 여 레코드를 완성 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-355">In the **Add Record** area, create a record using the values from the other row in the table, and then again select **Add**, **Save**, and **Yes** to complete the record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="cf7e9-356">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-356">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="cf7e9-357">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-357">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="cf7e9-358">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [Office 365에서 도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cf7e9-358">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
