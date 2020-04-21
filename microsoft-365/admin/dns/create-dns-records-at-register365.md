---
title: R 365에서 Microsoft에 대 한 DNS 레코드 만들기
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대 한 DNS 레코드를 Microsoft 용 R 365에 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 08db53df7510de76c6c5c33d2047cba4203324d8
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629266"
---
# <a name="create-dns-records-at-register365-for-microsoft"></a><span data-ttu-id="66e4f-103">R 365에서 Microsoft에 대 한 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="66e4f-103">Create DNS records at Register365 for Microsoft</span></span>

 <span data-ttu-id="66e4f-104">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="66e4f-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="66e4f-105">DNS 호스팅 공급자로 Register365를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-105">If Register365 is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="66e4f-106">다음은 추가할 기본 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-106">These are the main records to add.</span></span>  
  
- [<span data-ttu-id="66e4f-107">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="66e4f-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="66e4f-108">도메인에 대 한 전자 메일이 Microsoft에 제공 되도록 MX 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="66e4f-109">Microsoft에 필요한 6 개의 CNAME 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-109">Add the six CNAME records that are required for Microsoft</span></span>](#add-the-six-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="66e4f-110">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="66e4f-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="66e4f-111">Microsoft에 필요한 두 개의 SRV 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="66e4f-112">Microsoft에서 이러한 레코드를 추가 하 고 나면 도메인이 Microsoft 서비스에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-112">After you add these records at Microsoft, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="66e4f-113">Microsoft의 웹 사이트에 대 한 호스트 및 DNS에 대 한 자세한 내용은 [microsoft에서 공개 웹 사이트 사용](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66e4f-113">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="66e4f-p101">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66e4f-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="66e4f-117">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="66e4f-117">Add a TXT record for verification</span></span>
<span data-ttu-id="66e4f-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="66e4f-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="66e4f-119">Microsoft에서 도메인을 사용 하기 전에 사용자가 소유 하 고 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-119">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="66e4f-120">도메인 등록 기관에서 계정에 로그인 하 고 DNS 레코드를 만들 수 있는 기능은 Microsoft에 도메인을 소유 하 고 있음을 증명 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-120">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="66e4f-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="66e4f-p104">시작하려면 [이 링크](https://admin.register365.com/dns/)를 사용하여 Register365의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-p104">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![제어판 로그인 페이지](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="66e4f-126">**대시보드** 페이지에서 업데이트 중인 도메인 이름을 찾은 다음 드롭다운 목록에서 **DNS 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-126">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="66e4f-127">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="66e4f-127">(You may have to scroll down.)</span></span>
    
    ![목록에서 DNS 설정 선택](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="66e4f-129">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="66e4f-129">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="66e4f-130">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="66e4f-130">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="66e4f-131">행을 추가 해야 하는 경우 **a/CNAME 레코드 추가 (+)** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-131">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="66e4f-132">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="66e4f-132">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="66e4f-133">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="66e4f-133">**Host name**</span></span>|<span data-ttu-id="66e4f-134">**종류**</span><span class="sxs-lookup"><span data-stu-id="66e4f-134">**Type**</span></span>|<span data-ttu-id="66e4f-135">**결과**</span><span class="sxs-lookup"><span data-stu-id="66e4f-135">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="66e4f-136">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="66e4f-136">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="66e4f-137">TXT</span><span class="sxs-lookup"><span data-stu-id="66e4f-137">TXT</span></span>  <br/> |<span data-ttu-id="66e4f-138">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="66e4f-138">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="66e4f-139">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-139">**Note:** This is an example.</span></span> <span data-ttu-id="66e4f-140">표에서 특정 **대상 또는 지점** 값을 사용 하 여 여기서 주소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-140">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="66e4f-141">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="66e4f-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![DNS 영역 추가/수정 페이지에서 값 입력](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. <span data-ttu-id="66e4f-143">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-143">Select **Save**.</span></span>
    
    <span data-ttu-id="66e4f-144">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="66e4f-144">(You may have to scroll down.)</span></span>
    
    ![저장을 선택](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. <span data-ttu-id="66e4f-146">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-146">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="66e4f-147">도메인 등록 기관 사이트에서 레코드를 추가 했으므로 이제 Microsoft로 이동 하 여 레코드를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-147">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="66e4f-148">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-148">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="66e4f-149">I관리 센터에서 \*\* 설정 \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="66e4f-149">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="66e4f-150">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-150">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="66e4f-151">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-151">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="66e4f-152">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-152">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="66e4f-p106">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66e4f-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="66e4f-156">도메인에 대 한 전자 메일이 Microsoft에 제공 되도록 MX 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-156">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="66e4f-157"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="66e4f-157"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="66e4f-p107">시작하려면 [이 링크](https://admin.register365.com/dns/)를 사용하여 Register365의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-p107">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![제어판 로그인 페이지](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="66e4f-161">**대시보드** 페이지에서 업데이트 중인 도메인 이름을 찾은 다음 드롭다운 목록에서 **DNS 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-161">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="66e4f-162">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="66e4f-162">(You may have to scroll down.)</span></span>
    
    ![목록에서 DNS 설정 선택](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="66e4f-164">**Add/Modify DNS Zone**(DNS 영역 추가/수정) 페이지의 **Mail exchange records**(메일 교환 레코드) 구역에서 새 레코드의 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-164">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="66e4f-165">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="66e4f-165">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="66e4f-166">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="66e4f-166">**Host name**</span></span>|<span data-ttu-id="66e4f-167">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="66e4f-167">**Priority**</span></span>|<span data-ttu-id="66e4f-168">**결과**</span><span class="sxs-lookup"><span data-stu-id="66e4f-168">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="66e4f-169">(이 필드는 비워 둡니다.)</span><span class="sxs-lookup"><span data-stu-id="66e4f-169">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="66e4f-170">1 </span><span class="sxs-lookup"><span data-stu-id="66e4f-170">1</span></span>  <br/> <span data-ttu-id="66e4f-171">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66e4f-171">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="66e4f-172">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="66e4f-172">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="66e4f-173">**참고:** Microsoft 계정에서 \* \<도메인 키\> \* 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-173">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="66e4f-174">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="66e4f-174">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![DNS 영역 추가/수정 페이지에서 값 입력](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. <span data-ttu-id="66e4f-176">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-176">Select **Save**.</span></span>
    
    <span data-ttu-id="66e4f-177">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="66e4f-177">(You may have to scroll down.)</span></span>
    
    ![저장을 선택](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. <span data-ttu-id="66e4f-179">**Mail exchange records**(메일 교환 레코드) 구역에 다른 MX 레코드가 있으면 하나씩 선택한 후 키보드의 **Delete** 키를 눌러 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-179">If there are any other MX records in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. <span data-ttu-id="66e4f-181">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-181">Select **Save**.</span></span>
    
    <span data-ttu-id="66e4f-182">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="66e4f-182">(You may have to scroll down.)</span></span>
    
    ![저장을 선택](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="66e4f-184">Microsoft에 필요한 6 개의 CNAME 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-184">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="66e4f-185"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="66e4f-185"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="66e4f-p109">시작하려면 [이 링크](https://admin.register365.com/dns/)를 사용하여 Register365의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-p109">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![제어판 로그인 페이지](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="66e4f-189">**대시보드** 페이지에서 업데이트 중인 도메인 이름을 찾은 다음 드롭다운 목록에서 **DNS 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-189">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="66e4f-190">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="66e4f-190">(You may have to scroll down.)</span></span>
    
    ![목록에서 DNS 설정 선택](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="66e4f-192">**Add/Modify DNS Zone**(DNS 영역 추가/수정) 페이지의 **A, CNAME, AAAA, TXT and NS records**(A, CNAME, AAAA, TXT 및 NS 레코드) 구역에서 새 레코드의 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-192">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="66e4f-193">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="66e4f-193">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="66e4f-194">행을 추가 해야 하는 경우 **a/CNAME 레코드 추가 (+)** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-194">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="66e4f-195">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="66e4f-195">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="66e4f-196">\*\*\*\*Host name(호스트 이름)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="66e4f-196">\*\*\*\*Host name\*\*\*\*</span></span>|<span data-ttu-id="66e4f-197">\*\*\*\*Type(종류)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="66e4f-197">\*\*\*\*Type\*\*\*\*</span></span>|<span data-ttu-id="66e4f-198">\*\*\*\*결과\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="66e4f-198">\*\*\*\*Result\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="66e4f-199">autodiscover</span><span class="sxs-lookup"><span data-stu-id="66e4f-199">autodiscover</span></span>  <br/> |<span data-ttu-id="66e4f-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="66e4f-200">CNAME</span></span>  <br/> |<span data-ttu-id="66e4f-201">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="66e4f-201">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="66e4f-202">sip</span><span class="sxs-lookup"><span data-stu-id="66e4f-202">sip</span></span>  <br/> |<span data-ttu-id="66e4f-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="66e4f-203">CNAME</span></span>  <br/> |<span data-ttu-id="66e4f-204">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="66e4f-204">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="66e4f-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="66e4f-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="66e4f-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="66e4f-206">CNAME</span></span>  <br/> |<span data-ttu-id="66e4f-207">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="66e4f-207">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="66e4f-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="66e4f-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="66e4f-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="66e4f-209">CNAME</span></span>  <br/> |<span data-ttu-id="66e4f-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="66e4f-210">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="66e4f-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="66e4f-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="66e4f-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="66e4f-212">CNAME</span></span>  <br/> |<span data-ttu-id="66e4f-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="66e4f-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![DNS 영역 추가/수정 페이지에서 값 입력](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. <span data-ttu-id="66e4f-215">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-215">Select **Save**.</span></span>
    
    ![저장을 선택](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="66e4f-217">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="66e4f-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="66e4f-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="66e4f-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="66e4f-219">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="66e4f-220">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="66e4f-221">도메인에 대 한 SPF 레코드가 이미 있는 경우 Microsoft에 대해 새로 만들지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="66e4f-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="66e4f-222">대신, 두 값 집합을 모두 포함 하는 *단일* SPF 레코드가 있도록 현재 레코드에 필수 Microsoft 값을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="66e4f-p111">시작하려면 [이 링크](https://admin.register365.com/dns/)를 사용하여 Register365의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-p111">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![제어판 로그인 페이지](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="66e4f-226">**대시보드** 페이지에서 업데이트 중인 도메인 이름을 찾은 다음 드롭다운 목록에서 **DNS 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-226">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="66e4f-227">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="66e4f-227">(You may have to scroll down.)</span></span>
    
    ![목록에서 DNS 설정 선택](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="66e4f-229">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="66e4f-229">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="66e4f-230">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="66e4f-230">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="66e4f-231">행을 추가 해야 하는 경우 **a/CNAME 레코드 추가 (+)** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-231">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="66e4f-232">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="66e4f-232">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="66e4f-233">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="66e4f-233">**Host name**</span></span>|<span data-ttu-id="66e4f-234">**종류**</span><span class="sxs-lookup"><span data-stu-id="66e4f-234">**Type**</span></span>|<span data-ttu-id="66e4f-235">**결과**</span><span class="sxs-lookup"><span data-stu-id="66e4f-235">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="66e4f-236">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="66e4f-236">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="66e4f-237">TXT</span><span class="sxs-lookup"><span data-stu-id="66e4f-237">TXT</span></span>  <br/> |<span data-ttu-id="66e4f-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="66e4f-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="66e4f-239">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![DNS 영역 추가/수정 페이지에서 값 입력](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. <span data-ttu-id="66e4f-241">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-241">Select **Save**.</span></span>
    
    <span data-ttu-id="66e4f-242">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="66e4f-242">(You may have to scroll down.)</span></span>
    
    ![저장을 선택](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="66e4f-244">Microsoft에 필요한 두 개의 SRV 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-244">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="66e4f-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="66e4f-245"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="66e4f-p112">시작하려면 [이 링크](https://admin.register365.com/dns/)를 사용하여 Register365의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-p112">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![제어판 로그인 페이지](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="66e4f-249">**대시보드** 페이지에서 업데이트 중인 도메인 이름을 찾은 다음 드롭다운 목록에서 **DNS 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-249">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="66e4f-250">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="66e4f-250">(You may have to scroll down.)</span></span>
    
    ![목록에서 DNS 설정 선택](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="66e4f-252">**Add/Modify DNS Zone**(DNS 영역 추가/수정) 페이지의 **Service records**(서비스 레코드) 구역에서 새 레코드의 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-252">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="66e4f-253">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="66e4f-253">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="66e4f-254">**이름**</span><span class="sxs-lookup"><span data-stu-id="66e4f-254">**Name**</span></span>|<span data-ttu-id="66e4f-255">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="66e4f-255">**Priority**</span></span>|<span data-ttu-id="66e4f-256">**Weight(가중치)**</span><span class="sxs-lookup"><span data-stu-id="66e4f-256">**Weight**</span></span>|<span data-ttu-id="66e4f-257">**Port(포트)**</span><span class="sxs-lookup"><span data-stu-id="66e4f-257">**Port**</span></span>|<span data-ttu-id="66e4f-258">**결과**</span><span class="sxs-lookup"><span data-stu-id="66e4f-258">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="66e4f-259">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="66e4f-259">_sip._tls</span></span>  <br/> |<span data-ttu-id="66e4f-260">100</span><span class="sxs-lookup"><span data-stu-id="66e4f-260">100</span></span>  <br/> |<span data-ttu-id="66e4f-261">1 </span><span class="sxs-lookup"><span data-stu-id="66e4f-261">1</span></span>  <br/> |<span data-ttu-id="66e4f-262">443</span><span class="sxs-lookup"><span data-stu-id="66e4f-262">443</span></span>  <br/> |<span data-ttu-id="66e4f-263">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="66e4f-263">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="66e4f-264">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="66e4f-264">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="66e4f-265">100</span><span class="sxs-lookup"><span data-stu-id="66e4f-265">100</span></span>  <br/> |<span data-ttu-id="66e4f-266">1 </span><span class="sxs-lookup"><span data-stu-id="66e4f-266">1</span></span>  <br/> |<span data-ttu-id="66e4f-267">5061</span><span class="sxs-lookup"><span data-stu-id="66e4f-267">5061</span></span>  <br/> |<span data-ttu-id="66e4f-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="66e4f-268">sipfed.online.lync.com</span></span>  <br/> |
   
    ![서비스 레코드 섹션에 값 입력](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. <span data-ttu-id="66e4f-270">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66e4f-270">Select **Save**.</span></span>
    
    <span data-ttu-id="66e4f-271">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="66e4f-271">(You may have to scroll down.)</span></span>
    
    ![저장을 선택](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  <span data-ttu-id="66e4f-p113">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66e4f-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
