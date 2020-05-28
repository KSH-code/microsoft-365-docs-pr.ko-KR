---
title: 1&1gb OS에서 DNS 레코드 만들기
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대 한 DNS 레코드를 설정 하는 방법에 대해 설명 합니다 (예&1).
ms.openlocfilehash: 983fba73a6f82308d6d1bcf706ff93d72b98976c
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400596"
---
# <a name="create-dns-records-at-11-ionos-for-microsoft"></a><span data-ttu-id="e1356-103">1&1gb OS에서 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="e1356-103">Create DNS records at 1&1 IONOS for Microsoft</span></span>

 <span data-ttu-id="e1356-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="e1356-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="e1356-105">1&, 1gb OS는 도메인이 MX 레코드와 최상위 자동 검색 CNAME 레코드를 모두 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-105">Note that 1&1 IONOS doesn't allow a domain to have both an MX record and a top-level Autodiscover CNAME record.</span></span> <span data-ttu-id="e1356-106">이렇게 하면 Microsoft에 대해 Exchange Online을 구성 하는 방법이 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-106">This limits the ways in which you can configure Exchange Online for Microsoft.</span></span> <span data-ttu-id="e1356-107">해결 방법은 있지만 1&1gb OS에서 하위 도메인을 만든 경험이 이미 있는 경우에 **만** 이 방법을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-107">There is a workaround, but we recommend employing it **only** if you already have experience with creating subdomains at 1&1 IONOS.</span></span> <span data-ttu-id="e1356-108">>이 [서비스 제한은](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) 1&1gb os에서 자체 Microsoft DNS 레코드를 관리 하도록 선택 하는 경우에는이 문서의 단계에 따라 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 등에 대 한 DNS 레코드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-108">> If despite this [service limitation](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) you choose to manage your own Microsoft DNS records at 1&1 IONOS, follow the steps in this article to verify your domain and to set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="e1356-109">1&, 1gb OS에 이러한 레코드를 추가 하 고 나면 도메인은 Microsoft 서비스에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-109">After you add these records at 1&1 IONOS, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="e1356-110">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="e1356-110">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="e1356-111">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-111">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="e1356-112">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e1356-112">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e1356-113">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="e1356-113">Add a TXT record for verification</span></span>

<span data-ttu-id="e1356-p103">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e1356-p104">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="e1356-118">아래 단계를 따르거나 [비디오를 시청하세요(0:42에 시작)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span><span class="sxs-lookup"><span data-stu-id="e1356-118">Follow the steps below or [watch the video (start at 0:42)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
1. <span data-ttu-id="e1356-119">시작 하려면 [이 링크](https://my.1and1.com/)를 사용 하 여 1&1gb os의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-119">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="e1356-120">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="e1356-120">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="e1356-121">**도메인 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-121">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="e1356-122">**Domain Center (도메인 센터** ) 페이지에서 업데이트 하려는 도메인을 찾은 다음 해당 도메인에 대 한 **패널** ( **v**) 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-122">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="e1356-123">**도메인 설정** 영역에서 **DNS 설정 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-123">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="e1356-124">**TXT 및 SRV 레코드** 섹션에서 **레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-124">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="e1356-125">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="e1356-125">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e1356-126">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="e1356-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="e1356-127">**종류**</span><span class="sxs-lookup"><span data-stu-id="e1356-127">**Type**</span></span> <br/> |<span data-ttu-id="e1356-128">**Prefix(접두사)**</span><span class="sxs-lookup"><span data-stu-id="e1356-128">**Prefix**</span></span> <br/> |<span data-ttu-id="e1356-129">**Name Value(이름 값)**</span><span class="sxs-lookup"><span data-stu-id="e1356-129">**Name Value**</span></span> <br/> |
    |<span data-ttu-id="e1356-130">TXT</span><span class="sxs-lookup"><span data-stu-id="e1356-130">TXT</span></span>  <br/> |<span data-ttu-id="e1356-131">(이 필드를 비워 둠)</span><span class="sxs-lookup"><span data-stu-id="e1356-131">(Leave this field blank)</span></span>  <br/> |<span data-ttu-id="e1356-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="e1356-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="e1356-133">참고:이는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-133">NOTE: This is an example.</span></span> <span data-ttu-id="e1356-134">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="e1356-135">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="e1356-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="e1356-136">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-136">Select **Save**.</span></span>
    
8. <span data-ttu-id="e1356-137">**저장** 을 다시 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-137">Select **Save** again.</span></span> 
    
9. <span data-ttu-id="e1356-138">**DNS 설정 편집** 대화 상자에서 **예**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-138">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="e1356-139">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e1356-140">이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft 365로 돌아가서 Microsoft 365에 레코드를 찾을 것을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="e1356-141">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e1356-142">Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-142">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="e1356-143">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="e1356-144">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-144">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="e1356-145">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-145">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e1356-146">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="e1356-146">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="e1356-147">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-147">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="e1356-148">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e1356-148">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="e1356-149">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="e1356-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="e1356-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="e1356-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="e1356-151">아래 단계를 따르거나 [비디오를 시청하세요(3:22에 시작)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span><span class="sxs-lookup"><span data-stu-id="e1356-151">Follow the steps below or [watch the video (start at 3:22)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e1356-152">1und1.de에 등록 한 경우 [여기에 로그인](https://go.microsoft.com/fwlink/?linkid=859152)합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-152">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="e1356-153">시작 하려면 [이 링크](https://my.1and1.com/)를 사용 하 여 1&1gb os의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-153">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="e1356-154">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="e1356-154">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="e1356-155">**도메인 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-155">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="e1356-156">**Domain Center (도메인 센터** ) 페이지에서 업데이트 하려는 도메인을 찾은 다음 해당 도메인에 대 한 **패널** ( **v**) 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-156">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="e1356-157">**도메인 설정** 영역에서 **DNS 설정 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-157">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="e1356-158">**Mx 레코드** 섹션의 **메일 교환기 (mx 레코드)** 영역에서 **다른 메일 서버**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-158">In the **MX Records** section, in the **Mail Exchanger (MX Record)** area, select **Other mail server**.</span></span><br/><span data-ttu-id="e1356-159">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="e1356-159">(You may have to scroll down.)</span></span><br/><span data-ttu-id="e1356-160">![1 &amp; 1-BP-구성-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span><span class="sxs-lookup"><span data-stu-id="e1356-160">![1&amp;1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span></span> <br/>
  
6. <span data-ttu-id="e1356-161">MX 레코드가 이미 나열되어 있으면 레코드를 선택한 다음 키보드의 **Delete** 키를 눌러 하나씩 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-161">If there are any MX records already listed, delete each of them by selecting the record and then pressing the **Delete** key on your keyboard.</span></span><br/><span data-ttu-id="e1356-162">(MX 레코드가 나열되어 있지 않으면 다음 단계를 진행합니다.)</span><span class="sxs-lookup"><span data-stu-id="e1356-162">(If there are no MX records already listed, continue to the next step.)</span></span><br/><span data-ttu-id="e1356-163">![1 &amp; 1-BP-구성-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span><span class="sxs-lookup"><span data-stu-id="e1356-163">![1&amp;1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span></span><br/>
  
7. <span data-ttu-id="e1356-164">**MX 1** 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-164">In the boxes for the **MX 1** record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="e1356-165">**MX 1**</span><span class="sxs-lookup"><span data-stu-id="e1356-165">**MX 1**</span></span>|<span data-ttu-id="e1356-166">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="e1356-166">**Priority**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="e1356-167">*\<domain-key\>*. mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e1356-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <span data-ttu-id="e1356-168">참고: \<domain-key\> Microsoft 계정에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-168">NOTE: Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="e1356-169">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="e1356-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="e1356-170">10  </span><span class="sxs-lookup"><span data-stu-id="e1356-170">10</span></span>  <br/> <span data-ttu-id="e1356-171">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e1356-171">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | 
    
    ![1, 1-2 및 3 구성](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. <span data-ttu-id="e1356-173">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-173">Select **Save**.</span></span><br/><span data-ttu-id="e1356-174">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="e1356-174">(You may have to scroll down.)</span></span><br/><span data-ttu-id="e1356-175">![1 &amp; 1-BP-구성-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span><span class="sxs-lookup"><span data-stu-id="e1356-175">![1&amp;1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span></span>
  
9. <span data-ttu-id="e1356-176">**DNS 설정 편집** 대화 상자에서 **예**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-176">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="e1356-177">![DNS 설정 편집 대화 상자에서 예 선택](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="e1356-177">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="e1356-178">Microsoft에 필요한 6 개의 CNAME 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-178">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="e1356-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="e1356-179"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="e1356-180">1&에는 Microsoft 전자 메일 서비스에 필요한 CNAME 레코드와 함께 MX 레코드를 사용할 수 있도록 해결 방법이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-180">1&1 IONOS requires a workaround so that you can use an MX record together with the CNAME records that are required for Microsoft email services.</span></span> <span data-ttu-id="e1356-181">이 해결 방법을 사용 하려면 1&, 1gb OS의 하위 도메인 집합을 만들고이를 CNAME 레코드에 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-181">This workaround requires you to create a set of subdomains at 1&1 IONOS, and to assign them to CNAME records.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e1356-182">이 절차를 시작하기 전에 두 개 이상의 하위 도메인을 사용할 수 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="e1356-182">Make sure that you have at least two available subdomains before starting this procedure.</span></span> <span data-ttu-id="e1356-183">1&1gb OS에서 하위 도메인을 만든 경험이 이미 있는 경우에만이 솔루션을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-183">We recommend this solution only if you already have experience with creating subdomains at 1&1 IONOS.</span></span> 
  
### <a name="basic-cname-records"></a><span data-ttu-id="e1356-184">기본 CNAME 레코드</span><span class="sxs-lookup"><span data-stu-id="e1356-184">Basic CNAME records</span></span>

<span data-ttu-id="e1356-185">아래 단계를 따르거나 [비디오를 시청하세요(3:57에 시작)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span><span class="sxs-lookup"><span data-stu-id="e1356-185">Follow the steps below or [watch the video (start at 3:57)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e1356-186">1und1.de에 등록 한 경우 [여기에 로그인](https://go.microsoft.com/fwlink/?linkid=859152)합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-186">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="e1356-187">시작 하려면 [이 링크](https://my.1and1.com/)를 사용 하 여 1&1gb os의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-187">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="e1356-188">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="e1356-188">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="e1356-189">**도메인 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-189">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="e1356-190">**Domain Center (도메인 센터** ) 페이지에서 업데이트 하려는 도메인을 찾은 다음 하위 **도메인 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-190">On the **Domain Center** page, find the domain that you want to update, and then select **Manage Subdomains**.</span></span><br/><span data-ttu-id="e1356-191">![1 &amp; 1-BP-구성-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span><span class="sxs-lookup"><span data-stu-id="e1356-191">![1&amp;1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span></span> <br/><span data-ttu-id="e1356-192">두 개의 하위 도메인을 만들고 각 도메인에 대한 **별칭** 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-192">Now you'll create two subdomains and set an **Alias** value for each.</span></span><br/><span data-ttu-id="e1356-193">1&, 1gb OS는 최상위 CNAME 레코드를 하나만 지원 하기 때문에 필요 하지만 Microsoft에서는 여러 CNAME 레코드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-193">(This is required because 1&1 IONOS supports only one top-level CNAME record, but Microsoft requires several CNAME records.)</span></span><br/><span data-ttu-id="e1356-194">먼저 자동 검색 하위 도메인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-194">First, you'll create the Autodiscover subdomain.</span></span>
    
4. <span data-ttu-id="e1356-195">하위 **도메인 개요** 섹션에서 하위 **도메인 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-195">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
    ![1&amp;1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. <span data-ttu-id="e1356-p113">새 하위 도메인에 대한 **하위 도메인 만들기** 상자에 다음 표의 **하위 도메인 만들기** 값만 입력하거나 복사하여 붙여넣습니다. (이후 단계에서 **별칭** 값을 추가합니다.)</span><span class="sxs-lookup"><span data-stu-id="e1356-p113">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span>

    |<span data-ttu-id="e1356-199">**하위 도메인 만들기**</span><span class="sxs-lookup"><span data-stu-id="e1356-199">**Create Subdomain**</span></span>|<span data-ttu-id="e1356-200">**별칭**</span><span class="sxs-lookup"><span data-stu-id="e1356-200">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e1356-201">autodiscover</span><span class="sxs-lookup"><span data-stu-id="e1356-201">autodiscover</span></span>  <br/> |<span data-ttu-id="e1356-202">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e1356-202">autodiscover.outlook.com</span></span>   | 

    ![1 &amp; 1-BP-구성-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. <span data-ttu-id="e1356-204">하위 **도메인 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-204">Select **Create Subdomain**.</span></span><br/><span data-ttu-id="e1356-205">![1 &amp; 1-BP-구성-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span><span class="sxs-lookup"><span data-stu-id="e1356-205">![1&amp;1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span></span>
  
7. <span data-ttu-id="e1356-206">하위 **도메인 개요** 섹션에서 방금 만든 **자동 검색** 하위 도메인을 찾은 다음 해당 하위 도메인에 대 한 **패널 (v)** 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-206">In the **Subdomain Overview** section, locate the **autodiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="e1356-207">![1 &amp; 1-BP-구성-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span><span class="sxs-lookup"><span data-stu-id="e1356-207">![1&amp;1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span></span>
  
8. <span data-ttu-id="e1356-208">하위 **도메인 설정** 영역에서 **DNS 설정 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-208">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span> <br/><span data-ttu-id="e1356-209">![1 &amp; 1-BP-구성-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span><span class="sxs-lookup"><span data-stu-id="e1356-209">![1&amp;1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span></span>
  
9. <span data-ttu-id="e1356-210">**A/AAAA 레코드 (Ip 주소)** 섹션의 **Ip 주소 (레코드)** 영역에서 **CNAME**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-210">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span><br/><span data-ttu-id="e1356-211">![1 &amp; 1-BP-구성-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span><span class="sxs-lookup"><span data-stu-id="e1356-211">![1&amp;1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span></span>
  
10. <span data-ttu-id="e1356-212">**별칭:** 상자에서 다음 표의 **별칭** 값만 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-212">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span><br/> 
    
    |<span data-ttu-id="e1356-213">**하위 도메인 만들기**</span><span class="sxs-lookup"><span data-stu-id="e1356-213">**Create Subdomain**</span></span>|<span data-ttu-id="e1356-214">**별칭**</span><span class="sxs-lookup"><span data-stu-id="e1356-214">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e1356-215">autodiscover</span><span class="sxs-lookup"><span data-stu-id="e1356-215">autodiscover</span></span>  <br/> |<span data-ttu-id="e1356-216">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e1356-216">autodiscover.outlook.com</span></span>   |

    ![1 &amp; 1-BP-구성-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. <span data-ttu-id="e1356-218">고지 사항을 **알고 있음**에 대한 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-218">Select the check box for the **I am aware** disclaimer.</span></span><br/><span data-ttu-id="e1356-219">![1 &amp; 1-BP-구성-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span><span class="sxs-lookup"><span data-stu-id="e1356-219">![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span></span>
  
12. <span data-ttu-id="e1356-220">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-220">Select **Save**.</span></span><br/><span data-ttu-id="e1356-221">![1 &amp; 1-BP-구성-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span><span class="sxs-lookup"><span data-stu-id="e1356-221">![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span></span>
  
  
### <a name="additional-cname-records"></a><span data-ttu-id="e1356-222">추가 CNAME 레코드</span><span class="sxs-lookup"><span data-stu-id="e1356-222">Additional CNAME records</span></span>

<span data-ttu-id="e1356-p114">다음 절차에서 만든 추가 CNAME 레코드가 비즈니스용 Skype Online 서비스를 활성화합니다. 이미 만든 2개의 CNAME 레코드를 만들 때와 동일한 단계를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-p114">The additional CNAME records created in the following procedure enable Skype for Business Online services. You will employ the same steps that you used to create the two CNAME records you have already created.</span></span>
  
1. <span data-ttu-id="e1356-225">세 번째 하위 도메인(Lyncdiscover)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-225">Create the third subdomain (Lyncdiscover).</span></span><br/><span data-ttu-id="e1356-226">하위 **도메인 개요** 섹션에서 하위 **도메인 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-226">On the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
2. <span data-ttu-id="e1356-p115">새 하위 도메인에 대한 **하위 도메인 만들기** 상자에 다음 표의 **하위 도메인 만들기** 값만 입력하거나 복사하여 붙여넣습니다. (이후 단계에서 **별칭** 값을 추가합니다.)</span><span class="sxs-lookup"><span data-stu-id="e1356-p115">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span><br/> 
    
    |<span data-ttu-id="e1356-229">**하위 도메인 만들기**</span><span class="sxs-lookup"><span data-stu-id="e1356-229">**Create Subdomain**</span></span>|<span data-ttu-id="e1356-230">**별칭**</span><span class="sxs-lookup"><span data-stu-id="e1356-230">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e1356-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e1356-231">lyncdiscover</span></span>   |<span data-ttu-id="e1356-232">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e1356-232">webdir.online.lync.com</span></span>  |
   
3. <span data-ttu-id="e1356-233">하위 **도메인 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-233">Select **Create Subdomain**.</span></span>
    
4. <span data-ttu-id="e1356-234">**도메인 센터** 페이지에서 하위 도메인 **관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-234">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
5. <span data-ttu-id="e1356-235">하위 **도메인 개요** 섹션에서 방금 만든 **lyncdiscover** 하위 도메인을 찾은 다음 해당 하위 도메인에 대 한 **패널 (v)** 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-235">In the **Subdomain Overview** section, find the **lyncdiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="e1356-236">하위 **도메인 설정** 영역에서 **DNS 설정 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-236">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
6. <span data-ttu-id="e1356-237">**A/AAAA 레코드 (Ip 주소)** 섹션의 **Ip 주소 (레코드)** 영역에서 **CNAME**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-237">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span>
    
7. <span data-ttu-id="e1356-238">**별칭:** 상자에서 다음 표의 **별칭** 값만 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-238">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> <br/>
    
    |<span data-ttu-id="e1356-239">**하위 도메인 만들기**</span><span class="sxs-lookup"><span data-stu-id="e1356-239">**Create Subdomain**</span></span>|<span data-ttu-id="e1356-240">**별칭**</span><span class="sxs-lookup"><span data-stu-id="e1356-240">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e1356-241">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e1356-241">lyncdiscover</span></span>  <br/> |<span data-ttu-id="e1356-242">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e1356-242">webdir.online.lync.com</span></span>  <br/> |
   
8. <span data-ttu-id="e1356-243">**알고** 있는 고 지 사항에 대 한 확인란을 선택 하 고 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-243">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
9. <span data-ttu-id="e1356-244">**DNS 설정 편집** 대화 상자에서 **예**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-244">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="e1356-245">네 번째 하위 도메인(SIP)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-245">Create the fourth subdomain (SIP):</span></span> <br/><span data-ttu-id="e1356-246">하위 **도메인 개요** 섹션에서 하위 **도메인 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-246">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
11. <span data-ttu-id="e1356-p116">새 하위 도메인에 대한 **하위 도메인 만들기** 상자에 다음 표의 **하위 도메인 만들기** 값만 입력하거나 복사하여 붙여넣습니다. (이후 단계에서 **별칭** 값을 추가합니다.)</span><span class="sxs-lookup"><span data-stu-id="e1356-p116">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.) </span></span><br/>
    
    |<span data-ttu-id="e1356-249">**하위 도메인 만들기**</span><span class="sxs-lookup"><span data-stu-id="e1356-249">**Create Subdomain**</span></span>|<span data-ttu-id="e1356-250">**별칭**</span><span class="sxs-lookup"><span data-stu-id="e1356-250">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e1356-251">sip</span><span class="sxs-lookup"><span data-stu-id="e1356-251">sip</span></span>  <br/> |<span data-ttu-id="e1356-252">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e1356-252">sipdir.online.lync.com</span></span>  <br/> |
   
12. <span data-ttu-id="e1356-253">하위 **도메인 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-253">Select **Create Subdomain**.</span></span>
    
13. <span data-ttu-id="e1356-254">**도메인 센터** 페이지에서 하위 도메인 **관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-254">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
14. <span data-ttu-id="e1356-255">하위 **도메인 개요** 섹션에서 방금 만든 **sip** 하위 도메인을 찾은 다음 해당 하위 도메인에 대 한 **패널 (v)** 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-255">In the **Subdomain Overview** section, find the **sip** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="e1356-256">하위 **도메인 설정** 영역에서 **DNS 설정 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-256">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
15. <span data-ttu-id="e1356-257">**A/AAAA 레코드 (Ip 주소)** 섹션의 **Ip 주소 (레코드)** 영역에서 **CNAME**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-257">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span>
    
16. <span data-ttu-id="e1356-258">**별칭:** 상자에서 다음 표의 **별칭** 값만 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-258">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> 
    
    |<span data-ttu-id="e1356-259">**하위 도메인 만들기**</span><span class="sxs-lookup"><span data-stu-id="e1356-259">**Create Subdomain**</span></span>|<span data-ttu-id="e1356-260">**별칭**</span><span class="sxs-lookup"><span data-stu-id="e1356-260">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e1356-261">sip</span><span class="sxs-lookup"><span data-stu-id="e1356-261">sip</span></span>  <br/> |<span data-ttu-id="e1356-262">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e1356-262">sipdir.online.lync.com</span></span>  <br/> |
   
17. <span data-ttu-id="e1356-263">**알고** 있는 고 지 사항에 대 한 확인란을 선택 하 고 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-263">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
18. <span data-ttu-id="e1356-264">**DNS 설정 편집** 대화 상자에서 **예**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-264">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
### <a name="cname-records-needed-for-mdm"></a><span data-ttu-id="e1356-265">MDM에 필요한 CNAME 레코드</span><span class="sxs-lookup"><span data-stu-id="e1356-265">CNAME records needed for MDM</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e1356-266">다른 4개의 CNAME 레코드를 만드는 데 사용한 절차를 따르되 다음 표의 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-266">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> 
  
|<span data-ttu-id="e1356-267">**하위 도메인 만들기**</span><span class="sxs-lookup"><span data-stu-id="e1356-267">**Create Subdomain**</span></span>|<span data-ttu-id="e1356-268">**별칭**</span><span class="sxs-lookup"><span data-stu-id="e1356-268">**Alias**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e1356-269">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="e1356-269">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="e1356-270">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="e1356-270">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="e1356-271">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="e1356-271">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="e1356-272">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e1356-272">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e1356-273">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="e1356-273">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e1356-274">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-274">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e1356-275">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-275">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e1356-276">도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="e1356-276">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="e1356-277">대신, 두 값 집합을 모두 포함 하는 *단일* SPF 레코드가 있도록 현재 레코드에 필수 Microsoft 값을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-277">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="e1356-278">예제가 필요하세요?</span><span class="sxs-lookup"><span data-stu-id="e1356-278">Need examples?</span></span> <span data-ttu-id="e1356-279">[Microsoft에 대한 외부 Domain Name System 레코드](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e1356-279">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="e1356-280">SPF 레코드의 유효성을 검사 하기 위해 이러한[spf 유효성 검사 도구](../setup/domains-faq.md)중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-280">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
<span data-ttu-id="e1356-281">아래 단계를 따르거나 [비디오를 시청하세요(5:09에 시작)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span><span class="sxs-lookup"><span data-stu-id="e1356-281">Follow the steps below or [watch the video (start at 5:09)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e1356-282">1und1.de에 등록 한 경우 [여기에 로그인](https://go.microsoft.com/fwlink/?linkid=859152)합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-282">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="e1356-283">시작 하려면 [이 링크](https://my.1and1.com/)를 사용 하 여 1&1gb os의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-283">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="e1356-284">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="e1356-284">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="e1356-285">**도메인 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-285">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="e1356-286">**Domain Center (도메인 센터** ) 페이지에서 업데이트 하려는 도메인을 찾은 다음 해당 도메인에 대 한 **패널** (**v**) 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-286">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** (**v**) control for that domain.</span></span>
    
4. <span data-ttu-id="e1356-287">**도메인 설정** 영역에서 **DNS 설정 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-287">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="e1356-288">**TXT 및 SRV 레코드** 섹션에서 **레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-288">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="e1356-289">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="e1356-289">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="e1356-290">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="e1356-290">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> <br/><span data-ttu-id="e1356-291">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="e1356-291">(Choose the **Type** value from the drop-down list.)</span></span> <br/>
    
    |<span data-ttu-id="e1356-292">**종류**</span><span class="sxs-lookup"><span data-stu-id="e1356-292">**Type**</span></span>|<span data-ttu-id="e1356-293">**Prefix(접두사)**</span><span class="sxs-lookup"><span data-stu-id="e1356-293">**Prefix**</span></span>|<span data-ttu-id="e1356-294">**Name Value(이름 값)**</span><span class="sxs-lookup"><span data-stu-id="e1356-294">**Name Value**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="e1356-295">TXT</span><span class="sxs-lookup"><span data-stu-id="e1356-295">TXT</span></span>  <br/> |<span data-ttu-id="e1356-296">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="e1356-296">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="e1356-297">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="e1356-297">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="e1356-298">\*\*참고: \*\* 모든 간격이 올바르게 유지되도록 이 항목을 복사하여 붙여넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-298">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           | 
    
    ![TXT 레코드](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. <span data-ttu-id="e1356-300">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-300">Select **Save**.</span></span><br/><span data-ttu-id="e1356-301">![레코드 추가](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span><span class="sxs-lookup"><span data-stu-id="e1356-301">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span></span>
  
8. <span data-ttu-id="e1356-302">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-302">Select **Save**.</span></span><br/><span data-ttu-id="e1356-303">![레코드 저장](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span><span class="sxs-lookup"><span data-stu-id="e1356-303">![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span></span>
  
9. <span data-ttu-id="e1356-304">**DNS 설정 편집** 대화 상자에서 **예**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-304">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="e1356-305">![DNS 설정 편집 대화 상자에서 예 선택](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="e1356-305">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="e1356-306">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="e1356-306">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="e1356-307">아래 단계를 따르거나 [비디오를 시청하세요(5:51에 시작)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span><span class="sxs-lookup"><span data-stu-id="e1356-307">Follow the steps below or [watch the video (start at 5:51)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e1356-308">1und1.de에 등록 한 경우 [여기에 로그인](https://go.microsoft.com/fwlink/?linkid=859152)합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-308">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="e1356-309">시작 하려면 [이 링크](https://my.1and1.com/)를 사용 하 여 1&1gb os의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-309">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="e1356-310">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="e1356-310">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="e1356-311">**도메인 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-311">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="e1356-312">**Domain Center (도메인 센터** ) 페이지에서 업데이트 하려는 도메인을 찾은 다음 해당 도메인에 대 한 **패널** ( **v**) 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-312">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="e1356-313">**도메인 설정** 영역에서 **DNS 설정 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-313">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="e1356-314">**TXT 및 SRV 레코드** 섹션에서 **레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-314">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="e1356-315">처음 2개의 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-315">Add the first of the two SRV records.</span></span><br/><span data-ttu-id="e1356-316">**레코드 추가** 영역의 새 레코드용 상자에 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-316">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> <br/><span data-ttu-id="e1356-317">(드롭다운 목록에서 **Type (종류** ) 및 **TTL** 값을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="e1356-317">(Choose the **Type** and **TTL** values from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e1356-318">**유형**</span><span class="sxs-lookup"><span data-stu-id="e1356-318">**Type**</span></span>|<span data-ttu-id="e1356-319">**서비스**</span><span class="sxs-lookup"><span data-stu-id="e1356-319">**Service**</span></span>|<span data-ttu-id="e1356-320">**프로토콜**</span><span class="sxs-lookup"><span data-stu-id="e1356-320">**Protocol**</span></span>|<span data-ttu-id="e1356-321">**이름**</span><span class="sxs-lookup"><span data-stu-id="e1356-321">**Name**</span></span>|<span data-ttu-id="e1356-322">**호스트**</span><span class="sxs-lookup"><span data-stu-id="e1356-322">**Host**</span></span>|<span data-ttu-id="e1356-323">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="e1356-323">**Priority**</span></span>|<span data-ttu-id="e1356-324">**Weight(가중치)**</span><span class="sxs-lookup"><span data-stu-id="e1356-324">**Weight**</span></span>|<span data-ttu-id="e1356-325">**Port(포트)**</span><span class="sxs-lookup"><span data-stu-id="e1356-325">**Port**</span></span>|<span data-ttu-id="e1356-326">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e1356-326">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e1356-327">SRV</span><span class="sxs-lookup"><span data-stu-id="e1356-327">SRV</span></span>  <br/> |<span data-ttu-id="e1356-328">sip</span><span class="sxs-lookup"><span data-stu-id="e1356-328">sip</span></span>  <br/> |<span data-ttu-id="e1356-329">tls</span><span class="sxs-lookup"><span data-stu-id="e1356-329">tls</span></span>  <br/> |<span data-ttu-id="e1356-330">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="e1356-330">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="e1356-331">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e1356-331">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="e1356-332">100</span><span class="sxs-lookup"><span data-stu-id="e1356-332">100</span></span>  <br/> |<span data-ttu-id="e1356-333">1 </span><span class="sxs-lookup"><span data-stu-id="e1356-333">1</span></span>  <br/> |<span data-ttu-id="e1356-334">443</span><span class="sxs-lookup"><span data-stu-id="e1356-334">443</span></span>  <br/> |<span data-ttu-id="e1356-335">3600(1시간)</span><span class="sxs-lookup"><span data-stu-id="e1356-335">3600 (1 h)</span></span>  <br/> |
    |<span data-ttu-id="e1356-336">SRV</span><span class="sxs-lookup"><span data-stu-id="e1356-336">SRV</span></span>  <br/> |<span data-ttu-id="e1356-337">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="e1356-337">sipfederationtls</span></span>  <br/> |<span data-ttu-id="e1356-338">tcp</span><span class="sxs-lookup"><span data-stu-id="e1356-338">tcp</span></span>  <br/> |<span data-ttu-id="e1356-339">(이 필드는 비워 둡니다.)</span><span class="sxs-lookup"><span data-stu-id="e1356-339">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="e1356-340">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e1356-340">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="e1356-341">100</span><span class="sxs-lookup"><span data-stu-id="e1356-341">100</span></span>  <br/> |<span data-ttu-id="e1356-342">1 </span><span class="sxs-lookup"><span data-stu-id="e1356-342">1</span></span>  <br/> |<span data-ttu-id="e1356-343">5061</span><span class="sxs-lookup"><span data-stu-id="e1356-343">5061</span></span>  <br/> |<span data-ttu-id="e1356-344">3600(1시간)</span><span class="sxs-lookup"><span data-stu-id="e1356-344">3600 (1 h)</span></span>  <br/> |  
    
    ![1 &amp; 1-BP-구성-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. <span data-ttu-id="e1356-346">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-346">Select **Save**.</span></span> <br/><span data-ttu-id="e1356-347">![1 &amp; 1-BP-구성-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span><span class="sxs-lookup"><span data-stu-id="e1356-347">![1&amp;1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span></span>
  
8. <span data-ttu-id="e1356-348">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-348">Select **Save**.</span></span> <br/><span data-ttu-id="e1356-349">![1 &amp; 1-BP-구성-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span><span class="sxs-lookup"><span data-stu-id="e1356-349">![1&amp;1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span></span>
  
9. <span data-ttu-id="e1356-350">**DNS 설정 편집** 대화 상자에서 **예**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-350">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span> <br/><span data-ttu-id="e1356-351">![DNS 설정 편집 대화 상자에서 예 선택](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="e1356-351">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
10. <span data-ttu-id="e1356-352">다른 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-352">Add the other SRV record.</span></span> <br/><span data-ttu-id="e1356-353">**TXT 및 SRV 레코드** 섹션에서 **레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-353">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="e1356-354">**레코드 추가** 영역에서 표에 있는 다른 행의 값을 사용 하 여 레코드를 만든 다음 다시 **추가**, **저장**및 **예** 를 선택 하 여 레코드를 완성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-354">In the **Add Record** area, create a record using the values from the other row in the table, and then again select **Add**, **Save**, and **Yes** to complete the record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="e1356-355">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="e1356-355">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="e1356-356">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1356-356">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="e1356-357">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e1356-357">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
