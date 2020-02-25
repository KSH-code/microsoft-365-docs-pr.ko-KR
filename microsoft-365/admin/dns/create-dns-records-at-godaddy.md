---
title: GoDaddy에서 Office 365용 DNS 레코드 만들기
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
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 Office 365에 대 한 GoDaddy의 기타 서비스에 대 한 DNS 레코드를 설정 하는 방법을 알아봅니다.
ms.custom: okr_smb
ms.openlocfilehash: 4a67ef090c2b91c4cf1fdde376ab35e3a4ed4e20
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42245371"
---
# <a name="create-dns-records-at-godaddy-for-office-365"></a><span data-ttu-id="67745-103">GoDaddy에서 Office 365용 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="67745-103">Create DNS records at GoDaddy for Office 365</span></span>

 <span data-ttu-id="67745-104">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="67745-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="67745-105">DNS 호스팅 공급자로 GoDaddy를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="67745-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="67745-106">GoDaddy에서 이러한 레코드를 추가하고 나면 도메인이 Office 365 서비스에서 작동하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="67745-106">After you add these records at GoDaddy, your domain will be set up to work with Office 365 services.</span></span>

<span data-ttu-id="67745-107">Office 365에서 웹 사이트의 웹 호스팅 및 DNS에 대한 자세한 내용은 [Office 365에서 공개 웹 사이트 사용](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67745-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>

> [!NOTE]
> <span data-ttu-id="67745-p101">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67745-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="67745-111">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="67745-111">Add a TXT record for verification</span></span>
<span data-ttu-id="67745-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="67745-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="67745-p102">Office 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Office 365에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67745-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="67745-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67745-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="67745-117">아래 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="67745-117">Follow the steps below.</span></span>

1. <span data-ttu-id="67745-p104">시작하려면 [이 링크](https://account.godaddy.com/products/?go_redirect=disabled)를 사용하여 GoDaddy의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="67745-p104">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-구성-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="67745-121">**도메인**아래에서 편집 하려는 도메인의 DNS를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67745-121">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-구성-1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="67745-123">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67745-123">Select **Add**.</span></span>

    ![GoDaddy-BP-구성-1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="67745-125">드롭다운 목록에서 **TXT(텍스트)** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67745-125">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="67745-126">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="67745-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="67745-127">**Record type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="67745-127">**Record type**</span></span> |<span data-ttu-id="67745-128">**Host(호스트)**</span><span class="sxs-lookup"><span data-stu-id="67745-128">**Host**</span></span>|<span data-ttu-id="67745-129">**TXT VALUE(TXT 값)**</span><span class="sxs-lookup"><span data-stu-id="67745-129">**TXT Value**</span></span>|<span data-ttu-id="67745-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="67745-130">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="67745-131">TXT (텍스트)</span><span class="sxs-lookup"><span data-stu-id="67745-131">TXT (Text)</span></span>|@|<span data-ttu-id="67745-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="67745-132">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="67745-133">**참고**:이는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="67745-133">**Note**: This is an example.</span></span> <span data-ttu-id="67745-134">여기에는 Office 365의 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="67745-134">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="67745-135">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="67745-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="67745-136">1시간</span><span class="sxs-lookup"><span data-stu-id="67745-136">1 hour</span></span>  <br><span data-ttu-id="67745-137">(드롭다운 목록에서 값을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="67745-137">(Select a value from the drop-down list.)</span></span>|

      ![GoDaddy-1-0](../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="67745-139">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67745-139">Select **Save**.</span></span>

6. <span data-ttu-id="67745-140">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="67745-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="67745-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="67745-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>

<span data-ttu-id="67745-142">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="67745-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="67745-143">관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="67745-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="67745-144">**도메인** 페이지에서 확인 하려는 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67745-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="67745-145">**설정** 페이지에서 **설정 시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67745-145">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="67745-146">**도메인 확인** 페이지에서 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67745-146">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="67745-p107">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67745-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="67745-150">사용자 도메인의 전자 메일이 Office 365로 전송되도록 MX 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="67745-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="67745-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="67745-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="67745-152">아래 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="67745-152">Follow the steps below.</span></span>

1. <span data-ttu-id="67745-p108">시작하려면 [이 링크](https://account.godaddy.com/products/?go_redirect=disabled)를 사용하여 GoDaddy의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="67745-p108">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-구성-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="67745-156">**도메인**아래에서 편집 하려는 도메인의 DNS를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67745-156">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-구성-1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="67745-158">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67745-158">Select **Add**.</span></span>

    ![GoDaddy-BP-구성-1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="67745-160">드롭다운 목록에서 **MX(메일 교환기)** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67745-160">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![GoDaddy-BP-구성-2-0](../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="67745-162">새 레코드의 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="67745-162">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="67745-163">(드롭다운 목록에서 **TTL** 값을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="67745-163">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="67745-164">**Record type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="67745-164">**Record type**</span></span>|<span data-ttu-id="67745-165">**호스트**</span><span class="sxs-lookup"><span data-stu-id="67745-165">**Host**</span></span>|<span data-ttu-id="67745-166">**연결 대상**</span><span class="sxs-lookup"><span data-stu-id="67745-166">**Points to**</span></span>|<span data-ttu-id="67745-167">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="67745-167">**Priority**</span></span>|<span data-ttu-id="67745-168">**TTL**</span><span class="sxs-lookup"><span data-stu-id="67745-168">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="67745-169">MX (Mail Exchanger)(MX(메일 교환기))</span><span class="sxs-lookup"><span data-stu-id="67745-169">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="67745-170">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="67745-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="67745-171">**참고:** Office 365 계정에서 \* \<도메인\> 키\* 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="67745-171">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="67745-172">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="67745-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="67745-173">10 </span><span class="sxs-lookup"><span data-stu-id="67745-173">10</span></span>  <br/> <span data-ttu-id="67745-174">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67745-174">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="67745-175">1 hour</span><span class="sxs-lookup"><span data-stu-id="67745-175">1 hour</span></span>  <br/> |

6. <span data-ttu-id="67745-176">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67745-176">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="67745-177">Office 365에 필요한 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="67745-177">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="67745-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="67745-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="67745-179">아래 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="67745-179">Follow the steps below.</span></span>

1. <span data-ttu-id="67745-p110">시작하려면 [이 링크](https://account.godaddy.com/products/?go_redirect=disabled)를 사용하여 GoDaddy의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="67745-p110">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-구성-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="67745-183">**도메인**아래에서 편집 하려는 도메인의 DNS를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67745-183">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-구성-1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="67745-185">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67745-185">Select **Add**.</span></span>

    ![GoDaddy-BP-구성-1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="67745-187">드롭다운 목록에서 **CNAME(별칭)** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67745-187">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![GoDaddy-BP-구성-3-0](../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="67745-189">첫 번째 CNAME 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="67745-189">Create the first CNAME record.</span></span>

    <span data-ttu-id="67745-190">새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="67745-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="67745-191">(드롭다운 목록에서 **TTL** 값을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="67745-191">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="67745-192">**Record type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="67745-192">**Record type**</span></span>|<span data-ttu-id="67745-193">**호스트**</span><span class="sxs-lookup"><span data-stu-id="67745-193">**Host**</span></span>|<span data-ttu-id="67745-194">**연결 대상**</span><span class="sxs-lookup"><span data-stu-id="67745-194">**Points to**</span></span>|<span data-ttu-id="67745-195">**TTL**</span><span class="sxs-lookup"><span data-stu-id="67745-195">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="67745-196">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="67745-196">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="67745-197">autodiscover</span><span class="sxs-lookup"><span data-stu-id="67745-197">autodiscover</span></span>  <br/> |<span data-ttu-id="67745-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="67745-198">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="67745-199">1 hour</span><span class="sxs-lookup"><span data-stu-id="67745-199">1 hour</span></span>  <br/> |
    |<span data-ttu-id="67745-200">CNAME (Alias)(CNAME(별칭))</span><span class="sxs-lookup"><span data-stu-id="67745-200">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="67745-201">sip</span><span class="sxs-lookup"><span data-stu-id="67745-201">sip</span></span>  <br/> |<span data-ttu-id="67745-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="67745-202">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="67745-203">1시간</span><span class="sxs-lookup"><span data-stu-id="67745-203">1 hour</span></span>  <br/> |
    |<span data-ttu-id="67745-204">CNAME (Alias)(CNAME(별칭))</span><span class="sxs-lookup"><span data-stu-id="67745-204">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="67745-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="67745-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="67745-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="67745-206">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="67745-207">1시간</span><span class="sxs-lookup"><span data-stu-id="67745-207">1 hour</span></span>  <br/> |
    |<span data-ttu-id="67745-208">CNAME (Alias)(CNAME(별칭))</span><span class="sxs-lookup"><span data-stu-id="67745-208">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="67745-209">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="67745-209">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="67745-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="67745-210">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="67745-211">1시간</span><span class="sxs-lookup"><span data-stu-id="67745-211">1 hour</span></span>  <br/> |
    |<span data-ttu-id="67745-212">CNAME (Alias)(CNAME(별칭))</span><span class="sxs-lookup"><span data-stu-id="67745-212">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="67745-213">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="67745-213">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="67745-214">enterpriseenrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="67745-214">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="67745-215">1 hour</span><span class="sxs-lookup"><span data-stu-id="67745-215">1 hour</span></span>  <br/> |



6. <span data-ttu-id="67745-216">이 단계를 반복 하 여 CNAME 레코드 6 개를 모두 만들 때까지 다음 CNAME 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="67745-216">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="67745-217">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="67745-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="67745-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="67745-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="67745-219">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="67745-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="67745-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="67745-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="67745-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="67745-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="67745-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="67745-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="67745-223">아래 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="67745-223">Follow the steps below.</span></span>

1. <span data-ttu-id="67745-p112">시작하려면 [이 링크](https://account.godaddy.com/products/?go_redirect=disabled)를 사용하여 GoDaddy의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="67745-p112">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-구성-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="67745-227">**도메인**아래에서 편집 하려는 도메인의 DNS를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67745-227">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-구성-1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="67745-229">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67745-229">Select **Add**.</span></span>

    ![GoDaddy-BP-구성-1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="67745-231">드롭다운 목록에서 **TXT(텍스트)** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67745-231">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![GoDaddy-BP-구성-4-0](../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="67745-233">새 레코드의 상자에서 다음 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="67745-233">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="67745-234">(드롭다운 목록에서 **TTL** 값을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="67745-234">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="67745-235">**Record type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="67745-235">**Record type**</span></span>|<span data-ttu-id="67745-236">**Host(호스트)**</span><span class="sxs-lookup"><span data-stu-id="67745-236">**Host**</span></span>|<span data-ttu-id="67745-237">**TXT VALUE(TXT 값)**</span><span class="sxs-lookup"><span data-stu-id="67745-237">**TXT Value**</span></span>|<span data-ttu-id="67745-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="67745-238">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="67745-239">TXT (텍스트)</span><span class="sxs-lookup"><span data-stu-id="67745-239">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="67745-240">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="67745-240">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="67745-241">**참고:** 모든 공백이 올바르게 유지 되도록이 항목을 복사 하 여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="67745-241">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="67745-242">1 hour</span><span class="sxs-lookup"><span data-stu-id="67745-242">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-구성-4-1](../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="67745-244">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67745-244">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="67745-245">Office 365에 필요한 2개의 SRV 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="67745-245">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="67745-246"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="67745-246"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="67745-247">아래 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="67745-247">Follow the steps below.</span></span>

1. <span data-ttu-id="67745-p113">시작하려면 [이 링크](https://account.godaddy.com/products/?go_redirect=disabled)를 사용하여 GoDaddy의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="67745-p113">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-구성-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="67745-251">**도메인**아래에서 편집 하려는 도메인의 DNS를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67745-251">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-구성-1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="67745-253">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67745-253">Select **Add**.</span></span>

    ![GoDaddy-BP-구성-1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="67745-255">드롭다운 목록에서 **SRV(서비스)** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67745-255">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![GoDaddy-BP-구성-5-0](../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="67745-257">첫 번째 SRV 레코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="67745-257">Create the first SRV record.</span></span>

    <span data-ttu-id="67745-258">새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="67745-258">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="67745-259">(드롭다운 목록에서 **레코드 종류** 및 **TTL** 값을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="67745-259">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="67745-260">**Record type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="67745-260">**Record type**</span></span>|<span data-ttu-id="67745-261">**이름**</span><span class="sxs-lookup"><span data-stu-id="67745-261">**Name**</span></span>|<span data-ttu-id="67745-262">**대상**</span><span class="sxs-lookup"><span data-stu-id="67745-262">**Target**</span></span>|<span data-ttu-id="67745-263">**프로토콜**</span><span class="sxs-lookup"><span data-stu-id="67745-263">**Protocol**</span></span>|<span data-ttu-id="67745-264">**서비스**</span><span class="sxs-lookup"><span data-stu-id="67745-264">**Service**</span></span>|<span data-ttu-id="67745-265">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="67745-265">**Priority**</span></span>|<span data-ttu-id="67745-266">**가중치**</span><span class="sxs-lookup"><span data-stu-id="67745-266">**Weight**</span></span>|<span data-ttu-id="67745-267">**포트**</span><span class="sxs-lookup"><span data-stu-id="67745-267">**Port**</span></span>|<span data-ttu-id="67745-268">**TTL**</span><span class="sxs-lookup"><span data-stu-id="67745-268">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="67745-269">SRV (Service)(SRV(서비스))</span><span class="sxs-lookup"><span data-stu-id="67745-269">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="67745-270">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="67745-270">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="67745-271">_tls</span><span class="sxs-lookup"><span data-stu-id="67745-271">_tls</span></span>  <br/> |<span data-ttu-id="67745-272">_sip</span><span class="sxs-lookup"><span data-stu-id="67745-272">_sip</span></span>  <br/> |<span data-ttu-id="67745-273">100</span><span class="sxs-lookup"><span data-stu-id="67745-273">100</span></span>  <br/> |<span data-ttu-id="67745-274">개</span><span class="sxs-lookup"><span data-stu-id="67745-274">1</span></span>  <br/> |<span data-ttu-id="67745-275">443</span><span class="sxs-lookup"><span data-stu-id="67745-275">443</span></span>  <br/> |<span data-ttu-id="67745-276">1시간</span><span class="sxs-lookup"><span data-stu-id="67745-276">1 hour</span></span>  <br/> |
    |<span data-ttu-id="67745-277">SRV (Service)(SRV(서비스))</span><span class="sxs-lookup"><span data-stu-id="67745-277">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="67745-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="67745-278">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="67745-279">_tcp</span><span class="sxs-lookup"><span data-stu-id="67745-279">_tcp</span></span>  <br/> |<span data-ttu-id="67745-280">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="67745-280">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="67745-281">100</span><span class="sxs-lookup"><span data-stu-id="67745-281">100</span></span>  <br/> |<span data-ttu-id="67745-282">개</span><span class="sxs-lookup"><span data-stu-id="67745-282">1</span></span>  <br/> |<span data-ttu-id="67745-283">5061</span><span class="sxs-lookup"><span data-stu-id="67745-283">5061</span></span>  <br/> |<span data-ttu-id="67745-284">1시간</span><span class="sxs-lookup"><span data-stu-id="67745-284">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-구성-5-1](../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="67745-286">**5 단계** 를 반복 하 여 다른 SRV 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="67745-286">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="67745-287">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67745-287">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="67745-p114">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67745-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
