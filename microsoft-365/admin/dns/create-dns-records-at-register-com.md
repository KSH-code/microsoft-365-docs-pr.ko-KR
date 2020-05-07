---
title: Register.com에서 Microsoft에 대 한 DNS 레코드 만들기
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
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대 한 DNS 레코드를 Microsoft 용 Register.com에 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 125baf224cc9f3f21746a2f802b17f2572b65316
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048906"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a><span data-ttu-id="06a65-103">Register.com에서 Microsoft에 대 한 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="06a65-103">Create DNS records at Register.com for Microsoft</span></span>

 <span data-ttu-id="06a65-104">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="06a65-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="06a65-105">DNS 호스팅 공급자로 Register.com을 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-105">If Register.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="06a65-106">다음은 추가할 기본 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-106">These are the main records to add.</span></span> <span data-ttu-id="06a65-107">아래 단계를 따르거나 [비디오를 시청하세요](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="06a65-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
- [<span data-ttu-id="06a65-108">Register.com에서 TXT 레코드를 추가해 도메인을 소유하고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="06a65-108">Add a TXT record at Register.com to verify that you own the domain</span></span>](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [<span data-ttu-id="06a65-109">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="06a65-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="06a65-110">Microsoft에 필요한 CNAME 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="06a65-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="06a65-111">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="06a65-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [<span data-ttu-id="06a65-112">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="06a65-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="06a65-113">Register.com에서 이러한 레코드를 추가 하 고 나면 도메인이 Microsoft 서비스에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-113">After you add these records at Register.com, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="06a65-114">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="06a65-114">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="06a65-115">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-115">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="06a65-116">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06a65-116">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a><span data-ttu-id="06a65-117">Register.com에서 TXT 레코드를 추가해 도메인을 소유하고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="06a65-117">Add a TXT record at Register.com to verify that you own the domain</span></span>
<span data-ttu-id="06a65-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="06a65-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="06a65-p103">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="06a65-p104">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="06a65-123">아래 단계를 따르거나 [비디오를 시청하세요(0:44에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="06a65-123">Follow the steps below or [watch the video (start at 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="06a65-124">시작하려면 [이 링크](https://www.register.com/myaccount/)를 사용하여 Register.com의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-124">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="06a65-125">로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-125">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="06a65-126">**도메인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-126">Select **Domains**.</span></span>
    
3. <span data-ttu-id="06a65-127">**관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-127">Select **Manage**.</span></span>
    
4. <span data-ttu-id="06a65-128">수정 하려는 도메인 이름이 포함 된 행을 찾습니다. 그런 다음 해당 행에서 **관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-128">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="06a65-129">**고급 기술 설정** 섹션으로 스크롤한 후 **TXT 레코드 편집 (SPF)** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-129">Scroll down to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
6. <span data-ttu-id="06a65-130">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="06a65-130">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="06a65-131">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="06a65-131">**Host Name**</span></span> <br/> |<span data-ttu-id="06a65-132">**TXT Record**</span><span class="sxs-lookup"><span data-stu-id="06a65-132">**TXT Record**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="06a65-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="06a65-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="06a65-134">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-134">**Note:** This is an example.</span></span> <span data-ttu-id="06a65-135">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-135">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="06a65-136">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="06a65-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="06a65-137">**계속**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-137">Select **Continue**.</span></span>
    
8. <span data-ttu-id="06a65-138">다음 페이지에서 **계속** 을 다시 선택 하 여 변경 내용을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-138">On the next page, select **Continue** again to confirm your changes.</span></span> 
    
9. <span data-ttu-id="06a65-139">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="06a65-140">이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="06a65-141">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="06a65-142">I관리 센터에서 \*\* 설정 \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="06a65-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="06a65-143">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="06a65-144">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-144">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="06a65-145">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-145">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="06a65-146">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="06a65-146">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="06a65-147">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-147">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="06a65-148">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06a65-148">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="06a65-149">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="06a65-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="06a65-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="06a65-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="06a65-151">아래 단계를 따르거나 [비디오를 시청하세요(3:32에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="06a65-151">Follow the steps below or [watch the video (start at 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="06a65-152">시작하려면 [이 링크](https://www.register.com/myaccount/)를 사용하여 Register.com의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-152">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="06a65-153">로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-153">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="06a65-154">**도메인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-154">Select **Domains**.</span></span>
    
3. <span data-ttu-id="06a65-155">**관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-155">Select **Manage**.</span></span>
    
4. <span data-ttu-id="06a65-156">수정 하려는 도메인 이름이 포함 된 행을 찾습니다. 그런 다음 해당 행에서 **관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-156">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="06a65-157">**고급 기술 설정** 섹션으로 스크롤한 다음 **메일 교환기 레코드 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-157">Scroll to the **Advanced Technical Settings** section, and then select **Edit Mail Exchanger Records**.</span></span>
    
    ![메일 교환기 레코드 편집을 선택 합니다.](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. <span data-ttu-id="06a65-159">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="06a65-160">(드롭다운 목록에서 **Priority (우선 순위** ) 값을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="06a65-160">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="06a65-161">\*\*\*\*Host Name(호스트 이름)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="06a65-161">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="06a65-162">\*\*\*\*우선 순위\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="06a65-162">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="06a65-163">\*\*\*\*Mail Server(메일 서버)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="06a65-163">\*\*\*\*Mail Server\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="06a65-164">높음</span><span class="sxs-lookup"><span data-stu-id="06a65-164">High</span></span>  <br/> <span data-ttu-id="06a65-165">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06a65-165">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="06a65-166">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="06a65-166">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <br/><span data-ttu-id="06a65-167">**참고:** Microsoft 계정에서 \<*도메인-키*\>를 받으세요.</span><span class="sxs-lookup"><span data-stu-id="06a65-167">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> <br> [<span data-ttu-id="06a65-168">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="06a65-168">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![테이블의 값을 복사 하 여 붙여넣기](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. <span data-ttu-id="06a65-170">이미 나열된 다른 MX 레코드가 있으면 삭제할 레코드를 하나씩 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-170">If there were any other MX records already listed, select each of those records to be deleted.</span></span>
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. <span data-ttu-id="06a65-172">**계속**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-172">Select **Continue**.</span></span>
    
    ![계속을 선택](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. <span data-ttu-id="06a65-174">다음 페이지에서 **계속** 을 다시 선택 하 여 변경 내용을 확인 하 고 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-174">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![계속을 선택](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="06a65-176">Microsoft에 필요한 CNAME 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="06a65-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="06a65-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="06a65-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="06a65-178">아래 단계를 따르거나 [비디오를 시청하세요(4:23에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="06a65-178">Follow the steps below or [watch the video (start at 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="06a65-179">시작하려면 [이 링크](https://www.register.com/myaccount/)를 사용하여 Register.com의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-179">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="06a65-180">로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-180">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="06a65-181">**도메인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-181">Select **Domains**.</span></span>
    
3. <span data-ttu-id="06a65-182">**관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-182">Select **Manage**.</span></span>
    
4. <span data-ttu-id="06a65-183">수정 하려는 도메인 이름이 포함 된 행을 찾습니다. 그런 다음 해당 행에서 **관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-183">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="06a65-184">**고급 기술 설정** 섹션으로 스크롤한 다음 **도메인 별칭 레코드 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-184">Scroll to the **Advanced Technical Settings** section, and then select **Edit Domain Aliases Records**.</span></span>
    
    ![도메인 별칭 레코드 편집을 선택 합니다.](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. <span data-ttu-id="06a65-186">**도메인 별칭 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-186">Select **Add more domain aliases**.</span></span>
    
    ![다른 도메인 별칭 추가 선택](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. <span data-ttu-id="06a65-188">필요한 CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-188">Add the required CNAME records.</span></span>
    
    <span data-ttu-id="06a65-189">새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-189">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="06a65-190">\*\*\*\*첫 번째 필드(레이블이 지정되지 않음)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="06a65-190">\*\*\*\*First field (unlabeled)\*\*\*\*</span></span>|<span data-ttu-id="06a65-191">\*\*\*\*Points to(연결 대상)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="06a65-191">\*\*\*\*Points to\*\*\*\*</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="06a65-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="06a65-192">autodiscover</span></span>  <br/> |<span data-ttu-id="06a65-193">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="06a65-193">autodiscover.outlook.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="06a65-194">sip</span><span class="sxs-lookup"><span data-stu-id="06a65-194">sip</span></span>  <br/> |<span data-ttu-id="06a65-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="06a65-195">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="06a65-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="06a65-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="06a65-197">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="06a65-197">webdir.online.lync.com</span></span> <br/>  <br/> |
    |<span data-ttu-id="06a65-198">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="06a65-198">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="06a65-199">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="06a65-199">enterpriseregistration.windows.net</span></span>  <br/>  <br/> |
    |<span data-ttu-id="06a65-200">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="06a65-200">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="06a65-201">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="06a65-201">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/>  <br/> |
   
     ![테이블에서 DNS 값을 복사 하 여 붙여넣기](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. <span data-ttu-id="06a65-203">필요한 CNAME 레코드를 모두 추가한 경우 **계속**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-203">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![계속을 선택](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. <span data-ttu-id="06a65-205">다음 페이지에서 **계속** 을 다시 선택 하 여 변경 내용을 확인 하 고 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-205">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![계속을 선택](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="06a65-207">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="06a65-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="06a65-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="06a65-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="06a65-209">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-209">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="06a65-210">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="06a65-211">도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="06a65-211">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="06a65-212">대신, 필수 Microsoft 값을 현재 레코드에 추가하여 두 값 집합을 모두 포함하는 단일 SPF 레코드가 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-212">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span>  
  
<span data-ttu-id="06a65-213">아래 단계를 따르거나 [비디오를 시청하세요(5:12에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="06a65-213">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="06a65-214">시작하려면 [이 링크](https://www.register.com/myaccount/)를 사용하여 Register.com의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-214">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="06a65-215">로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-215">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="06a65-216">**도메인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-216">Select **Domains**.</span></span>
    
3. <span data-ttu-id="06a65-217">**관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-217">Select **Manage**.</span></span>
    
4. <span data-ttu-id="06a65-218">수정 하려는 도메인 이름이 포함 된 행을 찾습니다. 그런 다음 해당 행에서 **관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-218">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="06a65-219">**고급 기술 설정** 섹션으로 스크롤한 다음 **SPF (TXT 레코드 편집)** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-219">Scroll to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
    ![SPF (TXT 레코드 편집)을 선택 합니다.](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. <span data-ttu-id="06a65-221">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-221">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="06a65-222">\*\*\*\*Host Name(호스트 이름)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="06a65-222">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="06a65-223">\*\*\*\*TXT Record(TXT 레코드)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="06a65-223">\*\*\*\*TXT Record\*\*\*\*</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="06a65-224">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="06a65-224">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="06a65-225">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-225">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>  |
   
     ![테이블의 값을 복사 하 여 붙여넣기](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. <span data-ttu-id="06a65-227">**계속**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-227">Select **Continue**.</span></span>
    
    ![계속을 선택](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. <span data-ttu-id="06a65-229">다음 페이지에서 **계속** 을 다시 선택 하 여 변경 내용을 확인 하 고 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-229">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![계속을 선택](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="06a65-231">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="06a65-231">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="06a65-232"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="06a65-232"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="06a65-233">아래 단계를 따르거나 [비디오를 시청하세요(5:55에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="06a65-233">Follow the steps below or [watch the video (start at 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="06a65-p112">시작하려면 [이 링크](https://www.register.com/myaccount/)를 사용하여 Register.com의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-p112">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="06a65-236">**도메인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-236">Select **Domains**.</span></span>
    
3. <span data-ttu-id="06a65-237">**관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-237">Select **Manage**.</span></span>
    
4. <span data-ttu-id="06a65-238">수정 하려는 도메인 이름이 포함 된 행을 찾습니다. 그런 다음 해당 행에서 **관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-238">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="06a65-239">**고급 기술 설정** 섹션으로 스크롤한 다음 **SRV 레코드 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-239">Scroll to the **Advanced Technical Settings** section, and then select **Edit SRV Records**.</span></span>
    
    ![SRV 레코드 편집을 선택 합니다.](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. <span data-ttu-id="06a65-241">처음 2개의 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-241">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="06a65-242">새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다. </span><span class="sxs-lookup"><span data-stu-id="06a65-242">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="06a65-243">(드롭다운 목록에서 **Priority (우선 순위** ) 값을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="06a65-243">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="06a65-244">\*\*\*\*서비스\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="06a65-244">\*\*\*\*Service\*\*\*\*</span></span>|<span data-ttu-id="06a65-245">\*\*\*\*프로토콜\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="06a65-245">\*\*\*\*Proto\*\*\*\*</span></span>|<span data-ttu-id="06a65-246">\*\*\*\*이름\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="06a65-246">\*\*\*\*Name\*\*\*\*</span></span>|<span data-ttu-id="06a65-247">\*\*\*\*우선 순위\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="06a65-247">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="06a65-248">\*\*\*\*Weight(가중치)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="06a65-248">\*\*\*\*Weight\*\*\*\*</span></span>|<span data-ttu-id="06a65-249">\*\*\*\*포트\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="06a65-249">\*\*\*\*Port\*\*\*\*</span></span>|<span data-ttu-id="06a65-250">\*\*\*\*대상\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="06a65-250">\*\*\*\*Target\*\*\*\*</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="06a65-251">_sip</span><span class="sxs-lookup"><span data-stu-id="06a65-251">_sip</span></span>  <br/> |<span data-ttu-id="06a65-252">_tls</span><span class="sxs-lookup"><span data-stu-id="06a65-252">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="06a65-253">높음</span><span class="sxs-lookup"><span data-stu-id="06a65-253">High</span></span>  <br/> |<span data-ttu-id="06a65-254">개</span><span class="sxs-lookup"><span data-stu-id="06a65-254">1</span></span>  <br/> |<span data-ttu-id="06a65-255">443</span><span class="sxs-lookup"><span data-stu-id="06a65-255">443</span></span>  <br/> |<span data-ttu-id="06a65-256">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="06a65-256">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="06a65-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="06a65-257">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="06a65-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="06a65-258">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="06a65-259">높음</span><span class="sxs-lookup"><span data-stu-id="06a65-259">High</span></span>  <br/> |<span data-ttu-id="06a65-260">개</span><span class="sxs-lookup"><span data-stu-id="06a65-260">1</span></span>  <br/> |<span data-ttu-id="06a65-261">5061</span><span class="sxs-lookup"><span data-stu-id="06a65-261">5061</span></span>  <br/> |<span data-ttu-id="06a65-262">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="06a65-262">sipfed.online.lync.com</span></span>  <br/>  <br/> |
   
    ![테이블의 값을 복사 하 여 붙여넣기](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. <span data-ttu-id="06a65-264">**SRV 레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-264">Select **Add more SRV records**.</span></span>
    
    ![SRV 레코드 추가 선택](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. <span data-ttu-id="06a65-266">두 번째 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-266">Add the second SRV record:</span></span>
    
    <span data-ttu-id="06a65-267">위 표에 있는 두 번째 행의 값을 두 번째 레코드의 상자에 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-267">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
9. <span data-ttu-id="06a65-268">두 SRV 레코드를 모두 추가한 경우 **계속**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-268">When you have added both of the SRV records, select **Continue**.</span></span>
    
    ![계속을 선택](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. <span data-ttu-id="06a65-270">다음 페이지에서 **계속** 을 다시 선택 하 여 변경 내용을 확인 하 고 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-270">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![계속을 선택](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> <span data-ttu-id="06a65-272">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="06a65-272">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="06a65-273">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06a65-273">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="06a65-274">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06a65-274">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
