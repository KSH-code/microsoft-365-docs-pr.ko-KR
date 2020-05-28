---
title: Microsoft에 대 한 GoDaddy에서 DNS 레코드 만들기
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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online에 대 한 DNS 레코드를 설정 하 고 Microsoft의 GoDaddy에 게 보내는 기타 서비스에 대해 알아봅니다.
ms.openlocfilehash: 95bc9e1ca522796111bbf5146c93686bbbac1a3d
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400464"
---
# <a name="create-dns-records-at-godaddy-for-microsoft"></a><span data-ttu-id="e5028-103">Microsoft에 대 한 GoDaddy에서 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="e5028-103">Create DNS records at GoDaddy for Microsoft</span></span>

 <span data-ttu-id="e5028-104">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="e5028-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="e5028-105">DNS 호스팅 공급자로 GoDaddy를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="e5028-106">GoDaddy에 이러한 레코드를 추가 하 고 나면 도메인은 Microsoft 서비스에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-106">After you add these records at GoDaddy, your domain will be set up to work with Microsoft services.</span></span>

> [!NOTE]
> <span data-ttu-id="e5028-p101">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5028-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e5028-110">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="e5028-110">Add a TXT record for verification</span></span>
<span data-ttu-id="e5028-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="e5028-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="e5028-p102">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="e5028-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="e5028-116">아래 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-116">Follow the steps below.</span></span>

1. <span data-ttu-id="e5028-p104">시작하려면 [이 링크](https://account.godaddy.com/products/?go_redirect=disabled)를 사용하여 GoDaddy의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-p104">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-구성-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="e5028-120">**도메인**아래에서 편집 하려는 도메인의 DNS를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-120">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-구성-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="e5028-122">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-122">Select **Add**.</span></span>

    ![GoDaddy-BP-구성-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="e5028-124">드롭다운 목록에서 **TXT(텍스트)** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-124">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="e5028-125">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-125">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="e5028-126">**Record type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="e5028-126">**Record type**</span></span> |<span data-ttu-id="e5028-127">**Host(호스트)**</span><span class="sxs-lookup"><span data-stu-id="e5028-127">**Host**</span></span>|<span data-ttu-id="e5028-128">**TXT 값**</span><span class="sxs-lookup"><span data-stu-id="e5028-128">**TXT Value**</span></span>|<span data-ttu-id="e5028-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e5028-129">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e5028-130">TXT(텍스트)</span><span class="sxs-lookup"><span data-stu-id="e5028-130">TXT (Text)</span></span>|@|<span data-ttu-id="e5028-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="e5028-131">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="e5028-132">**참고**:이는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-132">**Note**: This is an example.</span></span> <span data-ttu-id="e5028-133">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="e5028-134">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="e5028-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="e5028-135">1시간</span><span class="sxs-lookup"><span data-stu-id="e5028-135">1 hour</span></span>  <br><span data-ttu-id="e5028-136">(드롭다운 목록에서 값을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="e5028-136">(Select a value from the drop-down list.)</span></span>|

      ![GoDaddy-1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="e5028-138">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-138">Select **Save**.</span></span>

6. <span data-ttu-id="e5028-139">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="e5028-140">이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>

<span data-ttu-id="e5028-141">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e5028-142">Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-142">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="e5028-143">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="e5028-144">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-144">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="e5028-145">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-145">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="e5028-p107">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5028-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="e5028-149">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="e5028-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="e5028-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="e5028-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="e5028-151">아래 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-151">Follow the steps below.</span></span>

1. <span data-ttu-id="e5028-p108">시작하려면 [이 링크](https://account.godaddy.com/products/?go_redirect=disabled)를 사용하여 GoDaddy의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-p108">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-구성-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="e5028-155">**도메인**아래에서 편집 하려는 도메인의 DNS를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-155">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-구성-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="e5028-157">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-157">Select **Add**.</span></span>

    ![GoDaddy-BP-구성-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="e5028-159">드롭다운 목록에서 **MX(메일 교환기)** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-159">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![GoDaddy-BP-구성-2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="e5028-161">새 레코드의 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-161">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="e5028-162">(드롭다운 목록에서 **TTL** 값을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="e5028-162">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="e5028-163">**Record type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="e5028-163">**Record type**</span></span>|<span data-ttu-id="e5028-164">**호스트**</span><span class="sxs-lookup"><span data-stu-id="e5028-164">**Host**</span></span>|<span data-ttu-id="e5028-165">**Points to(연결 대상)**</span><span class="sxs-lookup"><span data-stu-id="e5028-165">**Points to**</span></span>|<span data-ttu-id="e5028-166">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="e5028-166">**Priority**</span></span>|<span data-ttu-id="e5028-167">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e5028-167">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e5028-168">MX (Mail Exchanger)(MX(메일 교환기))</span><span class="sxs-lookup"><span data-stu-id="e5028-168">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="e5028-169">*\<domain-key\>*. mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e5028-169">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="e5028-170">**참고:** *\<domain-key\>* Microsoft 계정에서를 다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="e5028-170">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="e5028-171">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="e5028-171">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="e5028-172">10  </span><span class="sxs-lookup"><span data-stu-id="e5028-172">10</span></span>  <br/> <span data-ttu-id="e5028-173">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5028-173">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="e5028-174">1시간</span><span class="sxs-lookup"><span data-stu-id="e5028-174">1 hour</span></span>  <br/> |

6. <span data-ttu-id="e5028-175">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-175">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="e5028-176">Microsoft에 필요한 CNAME 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="e5028-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="e5028-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="e5028-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="e5028-178">아래 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-178">Follow the steps below.</span></span>

1. <span data-ttu-id="e5028-p110">시작하려면 [이 링크](https://account.godaddy.com/products/?go_redirect=disabled)를 사용하여 GoDaddy의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-p110">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-구성-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="e5028-182">**도메인**아래에서 편집 하려는 도메인의 DNS를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-182">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-구성-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="e5028-184">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-184">Select **Add**.</span></span>

    ![GoDaddy-BP-구성-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="e5028-186">드롭다운 목록에서 **CNAME(별칭)** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-186">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![GoDaddy-BP-구성-3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="e5028-188">첫 번째 CNAME 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-188">Create the first CNAME record.</span></span>

    <span data-ttu-id="e5028-189">새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다. </span><span class="sxs-lookup"><span data-stu-id="e5028-189">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="e5028-190">(드롭다운 목록에서 **TTL** 값을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="e5028-190">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="e5028-191">**Record type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="e5028-191">**Record type**</span></span>|<span data-ttu-id="e5028-192">**호스트**</span><span class="sxs-lookup"><span data-stu-id="e5028-192">**Host**</span></span>|<span data-ttu-id="e5028-193">**Points to(연결 대상)**</span><span class="sxs-lookup"><span data-stu-id="e5028-193">**Points to**</span></span>|<span data-ttu-id="e5028-194">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e5028-194">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e5028-195">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="e5028-195">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="e5028-196">autodiscover</span><span class="sxs-lookup"><span data-stu-id="e5028-196">autodiscover</span></span>  <br/> |<span data-ttu-id="e5028-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e5028-197">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="e5028-198">1시간</span><span class="sxs-lookup"><span data-stu-id="e5028-198">1 hour</span></span>  <br/> |
    |<span data-ttu-id="e5028-199">CNAME (Alias)(CNAME(별칭))</span><span class="sxs-lookup"><span data-stu-id="e5028-199">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="e5028-200">sip</span><span class="sxs-lookup"><span data-stu-id="e5028-200">sip</span></span>  <br/> |<span data-ttu-id="e5028-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e5028-201">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="e5028-202">1시간</span><span class="sxs-lookup"><span data-stu-id="e5028-202">1 hour</span></span>  <br/> |
    |<span data-ttu-id="e5028-203">CNAME (Alias)(CNAME(별칭))</span><span class="sxs-lookup"><span data-stu-id="e5028-203">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="e5028-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e5028-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="e5028-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e5028-205">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="e5028-206">1시간</span><span class="sxs-lookup"><span data-stu-id="e5028-206">1 hour</span></span>  <br/> |
    |<span data-ttu-id="e5028-207">CNAME (Alias)(CNAME(별칭))</span><span class="sxs-lookup"><span data-stu-id="e5028-207">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="e5028-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="e5028-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="e5028-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="e5028-209">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="e5028-210">1시간</span><span class="sxs-lookup"><span data-stu-id="e5028-210">1 hour</span></span>  <br/> |
    |<span data-ttu-id="e5028-211">CNAME (Alias)(CNAME(별칭))</span><span class="sxs-lookup"><span data-stu-id="e5028-211">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="e5028-212">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="e5028-212">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="e5028-213">enterpriseenrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e5028-213">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="e5028-214">1시간</span><span class="sxs-lookup"><span data-stu-id="e5028-214">1 hour</span></span>  <br/> |



6. <span data-ttu-id="e5028-215">이 단계를 반복 하 여 CNAME 레코드 6 개를 모두 만들 때까지 다음 CNAME 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-215">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e5028-216">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="e5028-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="e5028-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="e5028-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e5028-218">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e5028-219">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e5028-220">도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="e5028-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="e5028-221">대신, 두 값 집합을 모두 포함 하는 *단일* SPF 레코드가 있도록 현재 레코드에 필수 Microsoft 값을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="e5028-222">아래 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-222">Follow the steps below.</span></span>

1. <span data-ttu-id="e5028-p112">시작하려면 [이 링크](https://account.godaddy.com/products/?go_redirect=disabled)를 사용하여 GoDaddy의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-p112">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-구성-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="e5028-226">**도메인**아래에서 편집 하려는 도메인의 DNS를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-226">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-구성-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="e5028-228">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-228">Select **Add**.</span></span>

    ![GoDaddy-BP-구성-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="e5028-230">드롭다운 목록에서 **TXT(텍스트)** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-230">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![GoDaddy-BP-구성-4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="e5028-232">새 레코드의 상자에서 다음 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-232">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="e5028-233">(드롭다운 목록에서 **TTL** 값을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="e5028-233">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="e5028-234">**Record type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="e5028-234">**Record type**</span></span>|<span data-ttu-id="e5028-235">**Host(호스트)**</span><span class="sxs-lookup"><span data-stu-id="e5028-235">**Host**</span></span>|<span data-ttu-id="e5028-236">**TXT 값**</span><span class="sxs-lookup"><span data-stu-id="e5028-236">**TXT Value**</span></span>|<span data-ttu-id="e5028-237">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e5028-237">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e5028-238">TXT(텍스트)</span><span class="sxs-lookup"><span data-stu-id="e5028-238">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="e5028-239">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="e5028-239">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="e5028-240">\*\*참고: \*\* 모든 간격이 올바르게 유지되도록 이 항목을 복사하여 붙여넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-240">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="e5028-241">1시간</span><span class="sxs-lookup"><span data-stu-id="e5028-241">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-구성-4-1](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="e5028-243">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-243">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="e5028-244">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="e5028-244">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="e5028-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="e5028-245"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="e5028-246">아래 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-246">Follow the steps below.</span></span>

1. <span data-ttu-id="e5028-p113">시작하려면 [이 링크](https://account.godaddy.com/products/?go_redirect=disabled)를 사용하여 GoDaddy의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-p113">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-구성-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="e5028-250">**도메인**아래에서 편집 하려는 도메인의 DNS를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-250">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-구성-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="e5028-252">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-252">Select **Add**.</span></span>

    ![GoDaddy-BP-구성-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="e5028-254">드롭다운 목록에서 **SRV(서비스)** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-254">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![GoDaddy-BP-구성-5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="e5028-256">첫 번째 SRV 레코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-256">Create the first SRV record.</span></span>

    <span data-ttu-id="e5028-257">새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-257">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="e5028-258">(드롭다운 목록에서 **레코드 종류** 및 **TTL** 값을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="e5028-258">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="e5028-259">**Record type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="e5028-259">**Record type**</span></span>|<span data-ttu-id="e5028-260">**Name(이름)**</span><span class="sxs-lookup"><span data-stu-id="e5028-260">**Name**</span></span>|<span data-ttu-id="e5028-261">**Target(대상)**</span><span class="sxs-lookup"><span data-stu-id="e5028-261">**Target**</span></span>|<span data-ttu-id="e5028-262">**Protocol(프로토콜)**</span><span class="sxs-lookup"><span data-stu-id="e5028-262">**Protocol**</span></span>|<span data-ttu-id="e5028-263">**Service(서비스)**</span><span class="sxs-lookup"><span data-stu-id="e5028-263">**Service**</span></span>|<span data-ttu-id="e5028-264">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="e5028-264">**Priority**</span></span>|<span data-ttu-id="e5028-265">**Weight(가중치)**</span><span class="sxs-lookup"><span data-stu-id="e5028-265">**Weight**</span></span>|<span data-ttu-id="e5028-266">**Port(포트)**</span><span class="sxs-lookup"><span data-stu-id="e5028-266">**Port**</span></span>|<span data-ttu-id="e5028-267">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e5028-267">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e5028-268">SRV (Service)(SRV(서비스))</span><span class="sxs-lookup"><span data-stu-id="e5028-268">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="e5028-269">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e5028-269">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="e5028-270">_tls</span><span class="sxs-lookup"><span data-stu-id="e5028-270">_tls</span></span>  <br/> |<span data-ttu-id="e5028-271">_sip</span><span class="sxs-lookup"><span data-stu-id="e5028-271">_sip</span></span>  <br/> |<span data-ttu-id="e5028-272">100</span><span class="sxs-lookup"><span data-stu-id="e5028-272">100</span></span>  <br/> |<span data-ttu-id="e5028-273">1 </span><span class="sxs-lookup"><span data-stu-id="e5028-273">1</span></span>  <br/> |<span data-ttu-id="e5028-274">443</span><span class="sxs-lookup"><span data-stu-id="e5028-274">443</span></span>  <br/> |<span data-ttu-id="e5028-275">1시간</span><span class="sxs-lookup"><span data-stu-id="e5028-275">1 hour</span></span>  <br/> |
    |<span data-ttu-id="e5028-276">SRV (Service)(SRV(서비스))</span><span class="sxs-lookup"><span data-stu-id="e5028-276">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="e5028-277">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e5028-277">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="e5028-278">_tcp</span><span class="sxs-lookup"><span data-stu-id="e5028-278">_tcp</span></span>  <br/> |<span data-ttu-id="e5028-279">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="e5028-279">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="e5028-280">100</span><span class="sxs-lookup"><span data-stu-id="e5028-280">100</span></span>  <br/> |<span data-ttu-id="e5028-281">1 </span><span class="sxs-lookup"><span data-stu-id="e5028-281">1</span></span>  <br/> |<span data-ttu-id="e5028-282">5061</span><span class="sxs-lookup"><span data-stu-id="e5028-282">5061</span></span>  <br/> |<span data-ttu-id="e5028-283">1시간</span><span class="sxs-lookup"><span data-stu-id="e5028-283">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-구성-5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="e5028-285">**5 단계** 를 반복 하 여 다른 SRV 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-285">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="e5028-286">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e5028-286">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="e5028-p114">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5028-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
