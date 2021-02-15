---
title: Register365에서 Microsoft용 DNS 레코드 만들기
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: Microsoft용 Register365에서 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대한 DNS 레코드를 설정하는 방법을 배워야 합니다.
ms.openlocfilehash: 6cefdeff3da1256911d80066b55b00f5bef24055
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656918"
---
# <a name="create-dns-records-at-register365-for-microsoft"></a><span data-ttu-id="66569-103">Register365에서 Microsoft용 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="66569-103">Create DNS records at Register365 for Microsoft</span></span>

 <span data-ttu-id="66569-104">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.yml)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="66569-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="66569-105">DNS 호스팅 공급자로 Register365를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="66569-105">If Register365 is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="66569-106">다음은 추가할 기본 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="66569-106">These are the main records to add.</span></span>  
  
- [<span data-ttu-id="66569-107">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="66569-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="66569-108">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="66569-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="66569-109">Microsoft에 필요한 6개의 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="66569-109">Add the six CNAME records that are required for Microsoft</span></span>](#add-the-six-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="66569-110">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="66569-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="66569-111">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="66569-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="66569-112">Microsoft에서 이러한 레코드를 추가하고 나면 도메인이 Microsoft 서비스에서 작동할 수 있도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="66569-112">After you add these records at Microsoft, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="66569-p101">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66569-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="66569-116">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="66569-116">Add a TXT record for verification</span></span>
<span data-ttu-id="66569-117"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="66569-117"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="66569-p102">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66569-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="66569-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66569-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="66569-p104">시작하려면 [이 링크](https://admin.register365.com/dns/)를 사용하여 Register365의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="66569-p104">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![제어판 로그인 페이지](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="66569-125">**대시보드** 페이지에서 업데이트 중인 도메인 이름을 찾은 다음 드롭다운 목록에서 **DNS 설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66569-125">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="66569-126">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="66569-126">(You may have to scroll down.)</span></span>
    
    ![목록에서 DNS 설정 선택](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="66569-128">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="66569-128">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="66569-129">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="66569-129">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="66569-130">행을 추가해야 하는 경우 **A/CNAME 레코드 추가(+)를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66569-130">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="66569-131">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="66569-131">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="66569-132">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="66569-132">**Host name**</span></span>|<span data-ttu-id="66569-133">**종류**</span><span class="sxs-lookup"><span data-stu-id="66569-133">**Type**</span></span>|<span data-ttu-id="66569-134">**결과**</span><span class="sxs-lookup"><span data-stu-id="66569-134">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="66569-135">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="66569-135">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="66569-136">TXT</span><span class="sxs-lookup"><span data-stu-id="66569-136">TXT</span></span>  <br/> |<span data-ttu-id="66569-137">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="66569-137">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="66569-138">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="66569-138">**Note:** This is an example.</span></span> <span data-ttu-id="66569-139">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66569-139">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="66569-140">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="66569-140">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![DNS 영역 추가/수정 페이지에서 값 입력](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. <span data-ttu-id="66569-142">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66569-142">Select **Save**.</span></span>
    
    <span data-ttu-id="66569-143">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="66569-143">(You may have to scroll down.)</span></span>
    
    ![저장을 선택합니다.](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. <span data-ttu-id="66569-145">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="66569-145">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="66569-146">이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="66569-146">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="66569-147">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="66569-147">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="66569-148">I관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인</a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="66569-148">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="66569-149">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66569-149">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="66569-150">**설정** 페이지에서 **설정 시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66569-150">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="66569-151">**도메인 확인** 페이지에서 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66569-151">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="66569-p106">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66569-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="66569-155">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="66569-155">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="66569-156"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="66569-156"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="66569-p107">시작하려면 [이 링크](https://admin.register365.com/dns/)를 사용하여 Register365의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="66569-p107">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![제어판 로그인 페이지](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="66569-160">**대시보드** 페이지에서 업데이트 중인 도메인 이름을 찾은 다음 드롭다운 목록에서 **DNS 설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66569-160">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="66569-161">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="66569-161">(You may have to scroll down.)</span></span>
    
    ![목록에서 DNS 설정 선택](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="66569-163">**Add/Modify DNS Zone**(DNS 영역 추가/수정) 페이지의 **Mail exchange records**(메일 교환 레코드) 구역에서 새 레코드의 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="66569-163">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="66569-164">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="66569-164">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="66569-165">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="66569-165">**Host name**</span></span>|<span data-ttu-id="66569-166">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="66569-166">**Priority**</span></span>|<span data-ttu-id="66569-167">**결과**</span><span class="sxs-lookup"><span data-stu-id="66569-167">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="66569-168">(이 필드는 비워 둡니다.)</span><span class="sxs-lookup"><span data-stu-id="66569-168">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="66569-169">1 </span><span class="sxs-lookup"><span data-stu-id="66569-169">1</span></span>  <br/> <span data-ttu-id="66569-170">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66569-170">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="66569-171">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="66569-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="66569-172">**참고:** Microsoft  *\<domain-key\>*  계정에서 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="66569-172">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="66569-173">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="66569-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![DNS 영역 추가/수정 페이지에서 값 입력](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. <span data-ttu-id="66569-175">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66569-175">Select **Save**.</span></span>
    
    <span data-ttu-id="66569-176">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="66569-176">(You may have to scroll down.)</span></span>
    
    ![저장을 선택합니다.](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. <span data-ttu-id="66569-178">**Mail exchange records**(메일 교환 레코드) 구역에 다른 MX 레코드가 있으면 하나씩 선택한 후 키보드의 **Delete** 키를 눌러 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="66569-178">If there are any other MX records in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. <span data-ttu-id="66569-180">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66569-180">Select **Save**.</span></span>
    
    <span data-ttu-id="66569-181">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="66569-181">(You may have to scroll down.)</span></span>
    
    ![저장을 선택합니다.](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="66569-183">Microsoft에 필요한 6개의 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="66569-183">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="66569-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="66569-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="66569-p109">시작하려면 [이 링크](https://admin.register365.com/dns/)를 사용하여 Register365의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="66569-p109">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![제어판 로그인 페이지](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="66569-188">**대시보드** 페이지에서 업데이트 중인 도메인 이름을 찾은 다음 드롭다운 목록에서 **DNS 설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66569-188">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="66569-189">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="66569-189">(You may have to scroll down.)</span></span>
    
    ![목록에서 DNS 설정 선택](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="66569-191">**Add/Modify DNS Zone**(DNS 영역 추가/수정) 페이지의 **A, CNAME, AAAA, TXT and NS records**(A, CNAME, AAAA, TXT 및 NS 레코드) 구역에서 새 레코드의 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="66569-191">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="66569-192">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="66569-192">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="66569-193">행을 추가해야 하는 경우 **A/CNAME 레코드 추가(+)를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66569-193">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="66569-194">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="66569-194">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="66569-195">\*\*\*\*Host name(호스트 이름)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="66569-195">\*\*\*\*Host name\*\*\*\*</span></span>|<span data-ttu-id="66569-196">\*\*\*\*Type(종류)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="66569-196">\*\*\*\*Type\*\*\*\*</span></span>|<span data-ttu-id="66569-197">\*\*\*\*결과\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="66569-197">\*\*\*\*Result\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="66569-198">autodiscover</span><span class="sxs-lookup"><span data-stu-id="66569-198">autodiscover</span></span>  <br/> |<span data-ttu-id="66569-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="66569-199">CNAME</span></span>  <br/> |<span data-ttu-id="66569-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="66569-200">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="66569-201">sip</span><span class="sxs-lookup"><span data-stu-id="66569-201">sip</span></span>  <br/> |<span data-ttu-id="66569-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="66569-202">CNAME</span></span>  <br/> |<span data-ttu-id="66569-203">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="66569-203">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="66569-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="66569-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="66569-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="66569-205">CNAME</span></span>  <br/> |<span data-ttu-id="66569-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="66569-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="66569-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="66569-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="66569-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="66569-208">CNAME</span></span>  <br/> |<span data-ttu-id="66569-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="66569-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="66569-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="66569-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="66569-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="66569-211">CNAME</span></span>  <br/> |<span data-ttu-id="66569-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="66569-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![DNS 영역 추가/수정 페이지에서 값 입력](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. <span data-ttu-id="66569-214">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66569-214">Select **Save**.</span></span>
    
    ![저장을 선택합니다.](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="66569-216">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="66569-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="66569-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="66569-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="66569-218">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66569-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="66569-219">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66569-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="66569-220">도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="66569-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="66569-221">대신 두 값 집합을 모두 포함하는  *단일*  SPF 레코드가 있도록 현재 레코드에 필요한 Microsoft 값을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="66569-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="66569-p111">시작하려면 [이 링크](https://admin.register365.com/dns/)를 사용하여 Register365의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="66569-p111">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![제어판 로그인 페이지](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="66569-225">**대시보드** 페이지에서 업데이트 중인 도메인 이름을 찾은 다음 드롭다운 목록에서 **DNS 설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66569-225">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="66569-226">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="66569-226">(You may have to scroll down.)</span></span>
    
    ![목록에서 DNS 설정 선택](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="66569-228">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="66569-228">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="66569-229">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="66569-229">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="66569-230">행을 추가해야 하는 경우 **A/CNAME 레코드 추가(+)를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66569-230">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="66569-231">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="66569-231">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="66569-232">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="66569-232">**Host name**</span></span>|<span data-ttu-id="66569-233">**종류**</span><span class="sxs-lookup"><span data-stu-id="66569-233">**Type**</span></span>|<span data-ttu-id="66569-234">**결과**</span><span class="sxs-lookup"><span data-stu-id="66569-234">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="66569-235">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="66569-235">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="66569-236">TXT</span><span class="sxs-lookup"><span data-stu-id="66569-236">TXT</span></span>  <br/> |<span data-ttu-id="66569-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="66569-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="66569-238">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="66569-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![DNS 영역 추가/수정 페이지에서 값 입력](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. <span data-ttu-id="66569-240">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66569-240">Select **Save**.</span></span>
    
    <span data-ttu-id="66569-241">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="66569-241">(You may have to scroll down.)</span></span>
    
    ![저장을 선택합니다.](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="66569-243">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="66569-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="66569-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="66569-244"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="66569-p112">시작하려면 [이 링크](https://admin.register365.com/dns/)를 사용하여 Register365의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="66569-p112">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![제어판 로그인 페이지](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="66569-248">**대시보드** 페이지에서 업데이트 중인 도메인 이름을 찾은 다음 드롭다운 목록에서 **DNS 설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66569-248">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="66569-249">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="66569-249">(You may have to scroll down.)</span></span>
    
    ![목록에서 DNS 설정 선택](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="66569-251">**Add/Modify DNS Zone**(DNS 영역 추가/수정) 페이지의 **Service records**(서비스 레코드) 구역에서 새 레코드의 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="66569-251">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="66569-252">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="66569-252">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="66569-253">**이름**</span><span class="sxs-lookup"><span data-stu-id="66569-253">**Name**</span></span>|<span data-ttu-id="66569-254">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="66569-254">**Priority**</span></span>|<span data-ttu-id="66569-255">**Weight(가중치)**</span><span class="sxs-lookup"><span data-stu-id="66569-255">**Weight**</span></span>|<span data-ttu-id="66569-256">**Port(포트)**</span><span class="sxs-lookup"><span data-stu-id="66569-256">**Port**</span></span>|<span data-ttu-id="66569-257">**결과**</span><span class="sxs-lookup"><span data-stu-id="66569-257">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="66569-258">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="66569-258">_sip._tls</span></span>  <br/> |<span data-ttu-id="66569-259">100</span><span class="sxs-lookup"><span data-stu-id="66569-259">100</span></span>  <br/> |<span data-ttu-id="66569-260">1 </span><span class="sxs-lookup"><span data-stu-id="66569-260">1</span></span>  <br/> |<span data-ttu-id="66569-261">443</span><span class="sxs-lookup"><span data-stu-id="66569-261">443</span></span>  <br/> |<span data-ttu-id="66569-262">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="66569-262">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="66569-263">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="66569-263">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="66569-264">100</span><span class="sxs-lookup"><span data-stu-id="66569-264">100</span></span>  <br/> |<span data-ttu-id="66569-265">1 </span><span class="sxs-lookup"><span data-stu-id="66569-265">1</span></span>  <br/> |<span data-ttu-id="66569-266">5061</span><span class="sxs-lookup"><span data-stu-id="66569-266">5061</span></span>  <br/> |<span data-ttu-id="66569-267">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="66569-267">sipfed.online.lync.com</span></span>  <br/> |
   
    ![서비스 레코드 섹션에 값 입력](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. <span data-ttu-id="66569-269">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66569-269">Select **Save**.</span></span>
    
    <span data-ttu-id="66569-270">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="66569-270">(You may have to scroll down.)</span></span>
    
    ![저장을 선택합니다.](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  <span data-ttu-id="66569-p113">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66569-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
