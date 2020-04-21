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
ms.openlocfilehash: 8badcff89b2a8d8cc9901ef4f10c0a6b31de13d7
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629278"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a><span data-ttu-id="3a662-103">Register.com에서 Microsoft에 대 한 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="3a662-103">Create DNS records at Register.com for Microsoft</span></span>

 <span data-ttu-id="3a662-104">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a662-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="3a662-105">DNS 호스팅 공급자로 Register.com을 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-105">If Register.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="3a662-106">다음은 추가할 기본 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-106">These are the main records to add.</span></span> <span data-ttu-id="3a662-107">아래 단계를 따르거나 [비디오를 시청하세요](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="3a662-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
- [<span data-ttu-id="3a662-108">Register.com에서 TXT 레코드를 추가해 도메인을 소유하고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="3a662-108">Add a TXT record at Register.com to verify that you own the domain</span></span>](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [<span data-ttu-id="3a662-109">도메인에 대 한 전자 메일이 Microsoft에 제공 되도록 MX 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="3a662-110">Microsoft에 필요한 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="3a662-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="3a662-111">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="3a662-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [<span data-ttu-id="3a662-112">Microsoft에 필요한 두 개의 SRV 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="3a662-113">Register.com에서 이러한 레코드를 추가 하 고 나면 도메인이 Microsoft 서비스에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-113">After you add these records at Register.com, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="3a662-114">Microsoft의 웹 사이트에 대 한 호스트 및 DNS에 대 한 자세한 내용은 [microsoft에서 공개 웹 사이트 사용](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a662-114">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3a662-115">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="3a662-115">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="3a662-116">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-116">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="3a662-117">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제에 문제가 있는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a662-117">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a><span data-ttu-id="3a662-118">Register.com에서 TXT 레코드를 추가해 도메인을 소유하고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="3a662-118">Add a TXT record at Register.com to verify that you own the domain</span></span>
<span data-ttu-id="3a662-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="3a662-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="3a662-120">Microsoft에서 도메인을 사용 하기 전에 사용자가 소유 하 고 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-120">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="3a662-121">도메인 등록 기관에서 계정에 로그인 하 고 DNS 레코드를 만들 수 있는 기능은 Microsoft에 도메인을 소유 하 고 있음을 증명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-121">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3a662-p104">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="3a662-124">아래 단계를 따르거나 [비디오를 시청하세요(0:44에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="3a662-124">Follow the steps below or [watch the video (start at 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="3a662-125">시작하려면 [이 링크](https://www.register.com/myaccount/)를 사용하여 Register.com의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-125">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="3a662-126">로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-126">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="3a662-127">**도메인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-127">Select **Domains**.</span></span>
    
3. <span data-ttu-id="3a662-128">**관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-128">Select **Manage**.</span></span>
    
4. <span data-ttu-id="3a662-129">수정 하려는 도메인 이름이 포함 된 행을 찾습니다. 그런 다음 해당 행에서 **관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-129">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="3a662-130">**고급 기술 설정** 섹션으로 스크롤한 후 **TXT 레코드 편집 (SPF)** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-130">Scroll down to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
6. <span data-ttu-id="3a662-131">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3a662-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="3a662-132">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="3a662-132">**Host Name**</span></span> <br/> |<span data-ttu-id="3a662-133">**TXT Record**</span><span class="sxs-lookup"><span data-stu-id="3a662-133">**TXT Record**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="3a662-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="3a662-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="3a662-135">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-135">**Note:** This is an example.</span></span> <span data-ttu-id="3a662-136">표에서 특정 **대상 또는 지점** 값을 사용 하 여 여기서 주소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-136">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="3a662-137">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="3a662-137">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="3a662-138">**계속**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-138">Select **Continue**.</span></span>
    
8. <span data-ttu-id="3a662-139">다음 페이지에서 **계속** 을 다시 선택 하 여 변경 내용을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-139">On the next page, select **Continue** again to confirm your changes.</span></span> 
    
9. <span data-ttu-id="3a662-140">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="3a662-141">도메인 등록 기관 사이트에서 레코드를 추가 했으므로 이제 Microsoft로 이동 하 여 레코드를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="3a662-142">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="3a662-143">I관리 센터에서 \*\* 설정 \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="3a662-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="3a662-144">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="3a662-145">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-145">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="3a662-146">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-146">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3a662-147">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="3a662-147">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="3a662-148">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-148">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="3a662-149">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제에 문제가 있는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a662-149">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="3a662-150">도메인에 대 한 전자 메일이 Microsoft에 제공 되도록 MX 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="3a662-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="3a662-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="3a662-152">아래 단계를 따르거나 [비디오를 시청하세요(3:32에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="3a662-152">Follow the steps below or [watch the video (start at 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="3a662-153">시작하려면 [이 링크](https://www.register.com/myaccount/)를 사용하여 Register.com의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-153">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="3a662-154">로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-154">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="3a662-155">**도메인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-155">Select **Domains**.</span></span>
    
3. <span data-ttu-id="3a662-156">**관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-156">Select **Manage**.</span></span>
    
4. <span data-ttu-id="3a662-157">수정 하려는 도메인 이름이 포함 된 행을 찾습니다. 그런 다음 해당 행에서 **관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-157">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="3a662-158">**고급 기술 설정** 섹션으로 스크롤한 다음 **메일 교환기 레코드 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-158">Scroll to the **Advanced Technical Settings** section, and then select **Edit Mail Exchanger Records**.</span></span>
    
    ![메일 교환기 레코드 편집을 선택 합니다.](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. <span data-ttu-id="3a662-160">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-160">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="3a662-161">(드롭다운 목록에서 **Priority (우선 순위** ) 값을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="3a662-161">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3a662-162">\*\*\*\*Host Name(호스트 이름)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="3a662-162">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="3a662-163">\*\*\*\*우선 순위\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="3a662-163">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="3a662-164">\*\*\*\*Mail Server(메일 서버)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="3a662-164">\*\*\*\*Mail Server\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="3a662-165">높음</span><span class="sxs-lookup"><span data-stu-id="3a662-165">High</span></span>  <br/> <span data-ttu-id="3a662-166">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a662-166">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="3a662-167">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="3a662-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <br/><span data-ttu-id="3a662-168">**참고:** \<Microsoft 계정에서 *도메인 키* \> 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-168">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> <br> [<span data-ttu-id="3a662-169">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="3a662-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![테이블의 값을 복사 하 여 붙여넣기](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. <span data-ttu-id="3a662-171">이미 나열된 다른 MX 레코드가 있으면 삭제할 레코드를 하나씩 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-171">If there were any other MX records already listed, select each of those records to be deleted.</span></span>
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. <span data-ttu-id="3a662-173">**계속**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-173">Select **Continue**.</span></span>
    
    ![계속을 선택](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. <span data-ttu-id="3a662-175">다음 페이지에서 **계속** 을 다시 선택 하 여 변경 내용을 확인 하 고 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-175">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![계속을 선택](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="3a662-177">Microsoft에 필요한 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="3a662-177">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="3a662-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="3a662-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="3a662-179">아래 단계를 따르거나 [비디오를 시청하세요(4:23에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="3a662-179">Follow the steps below or [watch the video (start at 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="3a662-180">시작하려면 [이 링크](https://www.register.com/myaccount/)를 사용하여 Register.com의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-180">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="3a662-181">로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-181">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="3a662-182">**도메인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-182">Select **Domains**.</span></span>
    
3. <span data-ttu-id="3a662-183">**관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-183">Select **Manage**.</span></span>
    
4. <span data-ttu-id="3a662-184">수정 하려는 도메인 이름이 포함 된 행을 찾습니다. 그런 다음 해당 행에서 **관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-184">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="3a662-185">**고급 기술 설정** 섹션으로 스크롤한 다음 **도메인 별칭 레코드 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-185">Scroll to the **Advanced Technical Settings** section, and then select **Edit Domain Aliases Records**.</span></span>
    
    ![도메인 별칭 레코드 편집을 선택 합니다.](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. <span data-ttu-id="3a662-187">**도메인 별칭 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-187">Select **Add more domain aliases**.</span></span>
    
    ![다른 도메인 별칭 추가 선택](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. <span data-ttu-id="3a662-189">필요한 CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-189">Add the required CNAME records.</span></span>
    
    <span data-ttu-id="3a662-190">새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="3a662-191">\*\*\*\*첫 번째 필드(레이블이 지정되지 않음)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="3a662-191">\*\*\*\*First field (unlabeled)\*\*\*\*</span></span>|<span data-ttu-id="3a662-192">\*\*\*\*Points to(연결 대상)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="3a662-192">\*\*\*\*Points to\*\*\*\*</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="3a662-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="3a662-193">autodiscover</span></span>  <br/> |<span data-ttu-id="3a662-194">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="3a662-194">autodiscover.outlook.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="3a662-195">sip</span><span class="sxs-lookup"><span data-stu-id="3a662-195">sip</span></span>  <br/> |<span data-ttu-id="3a662-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3a662-196">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="3a662-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="3a662-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="3a662-198">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3a662-198">webdir.online.lync.com</span></span> <br/>  <br/> |
    |<span data-ttu-id="3a662-199">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="3a662-199">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="3a662-200">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="3a662-200">enterpriseregistration.windows.net</span></span>  <br/>  <br/> |
    |<span data-ttu-id="3a662-201">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="3a662-201">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="3a662-202">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3a662-202">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/>  <br/> |
   
     ![테이블에서 DNS 값을 복사 하 여 붙여넣기](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. <span data-ttu-id="3a662-204">필요한 CNAME 레코드를 모두 추가한 경우 **계속**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-204">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![계속을 선택](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. <span data-ttu-id="3a662-206">다음 페이지에서 **계속** 을 다시 선택 하 여 변경 내용을 확인 하 고 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-206">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![계속을 선택](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="3a662-208">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="3a662-208">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="3a662-209"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="3a662-209"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="3a662-210">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-210">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="3a662-211">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-211">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="3a662-212">도메인에 대 한 SPF 레코드가 이미 있는 경우 Microsoft에 대해 새로 만들지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="3a662-212">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="3a662-213">대신, 두 값 집합을 모두 포함 하는 단일 SPF 레코드가 있도록 현재 레코드에 필수 Microsoft 값을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-213">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span>  
  
<span data-ttu-id="3a662-214">아래 단계를 따르거나 [비디오를 시청하세요(5:12에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="3a662-214">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="3a662-215">시작하려면 [이 링크](https://www.register.com/myaccount/)를 사용하여 Register.com의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-215">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="3a662-216">로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-216">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="3a662-217">**도메인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-217">Select **Domains**.</span></span>
    
3. <span data-ttu-id="3a662-218">**관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-218">Select **Manage**.</span></span>
    
4. <span data-ttu-id="3a662-219">수정 하려는 도메인 이름이 포함 된 행을 찾습니다. 그런 다음 해당 행에서 **관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-219">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="3a662-220">**고급 기술 설정** 섹션으로 스크롤한 다음 **SPF (TXT 레코드 편집)** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-220">Scroll to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
    ![SPF (TXT 레코드 편집)을 선택 합니다.](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. <span data-ttu-id="3a662-222">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-222">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="3a662-223">\*\*\*\*Host Name(호스트 이름)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="3a662-223">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="3a662-224">\*\*\*\*TXT Record(TXT 레코드)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="3a662-224">\*\*\*\*TXT Record\*\*\*\*</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="3a662-225">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="3a662-225">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="3a662-226">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-226">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>  |
   
     ![테이블의 값을 복사 하 여 붙여넣기](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. <span data-ttu-id="3a662-228">**계속**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-228">Select **Continue**.</span></span>
    
    ![계속을 선택](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. <span data-ttu-id="3a662-230">다음 페이지에서 **계속** 을 다시 선택 하 여 변경 내용을 확인 하 고 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-230">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![계속을 선택](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="3a662-232">Microsoft에 필요한 두 개의 SRV 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-232">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="3a662-233"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="3a662-233"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="3a662-234">아래 단계를 따르거나 [비디오를 시청하세요(5:55에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="3a662-234">Follow the steps below or [watch the video (start at 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="3a662-p112">시작하려면 [이 링크](https://www.register.com/myaccount/)를 사용하여 Register.com의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-p112">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="3a662-237">**도메인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-237">Select **Domains**.</span></span>
    
3. <span data-ttu-id="3a662-238">**관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-238">Select **Manage**.</span></span>
    
4. <span data-ttu-id="3a662-239">수정 하려는 도메인 이름이 포함 된 행을 찾습니다. 그런 다음 해당 행에서 **관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-239">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="3a662-240">**고급 기술 설정** 섹션으로 스크롤한 다음 **SRV 레코드 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-240">Scroll to the **Advanced Technical Settings** section, and then select **Edit SRV Records**.</span></span>
    
    ![SRV 레코드 편집을 선택 합니다.](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. <span data-ttu-id="3a662-242">처음 2개의 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-242">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="3a662-243">새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-243">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="3a662-244">(드롭다운 목록에서 **Priority (우선 순위** ) 값을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="3a662-244">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3a662-245">\*\*\*\*서비스\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="3a662-245">\*\*\*\*Service\*\*\*\*</span></span>|<span data-ttu-id="3a662-246">\*\*\*\*프로토콜\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="3a662-246">\*\*\*\*Proto\*\*\*\*</span></span>|<span data-ttu-id="3a662-247">\*\*\*\*이름\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="3a662-247">\*\*\*\*Name\*\*\*\*</span></span>|<span data-ttu-id="3a662-248">\*\*\*\*우선 순위\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="3a662-248">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="3a662-249">\*\*\*\*Weight(가중치)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="3a662-249">\*\*\*\*Weight\*\*\*\*</span></span>|<span data-ttu-id="3a662-250">\*\*\*\*포트\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="3a662-250">\*\*\*\*Port\*\*\*\*</span></span>|<span data-ttu-id="3a662-251">\*\*\*\*대상\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="3a662-251">\*\*\*\*Target\*\*\*\*</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3a662-252">_sip</span><span class="sxs-lookup"><span data-stu-id="3a662-252">_sip</span></span>  <br/> |<span data-ttu-id="3a662-253">_tls</span><span class="sxs-lookup"><span data-stu-id="3a662-253">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="3a662-254">높음</span><span class="sxs-lookup"><span data-stu-id="3a662-254">High</span></span>  <br/> |<span data-ttu-id="3a662-255">1 </span><span class="sxs-lookup"><span data-stu-id="3a662-255">1</span></span>  <br/> |<span data-ttu-id="3a662-256">443</span><span class="sxs-lookup"><span data-stu-id="3a662-256">443</span></span>  <br/> |<span data-ttu-id="3a662-257">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3a662-257">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="3a662-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="3a662-258">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="3a662-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="3a662-259">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="3a662-260">높음</span><span class="sxs-lookup"><span data-stu-id="3a662-260">High</span></span>  <br/> |<span data-ttu-id="3a662-261">1 </span><span class="sxs-lookup"><span data-stu-id="3a662-261">1</span></span>  <br/> |<span data-ttu-id="3a662-262">5061</span><span class="sxs-lookup"><span data-stu-id="3a662-262">5061</span></span>  <br/> |<span data-ttu-id="3a662-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3a662-263">sipfed.online.lync.com</span></span>  <br/>  <br/> |
   
    ![테이블의 값을 복사 하 여 붙여넣기](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. <span data-ttu-id="3a662-265">**SRV 레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-265">Select **Add more SRV records**.</span></span>
    
    ![SRV 레코드 추가 선택](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. <span data-ttu-id="3a662-267">두 번째 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-267">Add the second SRV record:</span></span>
    
    <span data-ttu-id="3a662-268">위 표에 있는 두 번째 행의 값을 두 번째 레코드의 상자에 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-268">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
9. <span data-ttu-id="3a662-269">두 SRV 레코드를 모두 추가한 경우 **계속**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-269">When you have added both of the SRV records, select **Continue**.</span></span>
    
    ![계속을 선택](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. <span data-ttu-id="3a662-271">다음 페이지에서 **계속** 을 다시 선택 하 여 변경 내용을 확인 하 고 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-271">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![계속을 선택](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> <span data-ttu-id="3a662-273">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="3a662-273">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="3a662-274">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a662-274">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="3a662-275">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제에 문제가 있는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a662-275">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
