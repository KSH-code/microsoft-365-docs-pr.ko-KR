---
title: Wix for Office 365에서 DNS 레코드 만들기
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 Office 365 용 Wix의 기타 서비스에 대 한 DNS 레코드를 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 43d2f2417153dd0c848c33736733237b1681c02c
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42246895"
---
# <a name="create-dns-records-at-wix-for-office-365"></a><span data-ttu-id="2adb0-103">Wix for Office 365에서 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="2adb0-103">Create DNS records at Wix for Office 365</span></span>

 <span data-ttu-id="2adb0-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="2adb0-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="2adb0-105">Wix가 DNS 호스팅 공급자 이면이 문서에 나와 있는 단계에 따라 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 등에 대 한 DNS 레코드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="2adb0-106">다음은 추가할 기본 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="2adb0-107">[확인을 위해 TXT 레코드를 추가](#add-a-txt-record-for-verification)합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="2adb0-108">[도메인에 대 한 전자 메일이 Office 365에 제공 되도록 MX 레코드를 추가](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-108">[Add an MX record so email for your domain will come to Office 365](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365).</span></span>
    
- <span data-ttu-id="2adb0-109">[Office 365에 필요한 다섯 개의 CNAME 레코드를 추가](#add-the-five-cname-records-that-are-required-for-office-365)합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-109">[Add the five CNAME records that are required for Office 365](#add-the-five-cname-records-that-are-required-for-office-365).</span></span>
    
- <span data-ttu-id="2adb0-110">[SPF에 대 한 TXT 레코드를 추가 하 여 전자 메일 스팸 방지](#add-a-txt-record-for-spf-to-help-prevent-email-spam)</span><span class="sxs-lookup"><span data-stu-id="2adb0-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="2adb0-111">[Office 365에 필요한 두 개의 SRV 레코드를 추가](#add-the-two-srv-records-that-are-required-for-office-365)합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-111">[Add the two SRV records that are required for Office 365](#add-the-two-srv-records-that-are-required-for-office-365).</span></span>
    
<span data-ttu-id="2adb0-112">Wix에서 이러한 레코드를 추가 하 고 나면 도메인이 Office 365 서비스에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-112">After you add these records at Wix, your domain will be set up to work with Office 365 services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="2adb0-p101">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2adb0-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="2adb0-116">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="2adb0-116">Add a TXT record for verification</span></span>
<span data-ttu-id="2adb0-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="2adb0-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="2adb0-p102">Office 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Office 365에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2adb0-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="2adb0-122">시작 하려면 [이 링크](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)를 사용 하 여 Wix의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-122">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="2adb0-123">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="2adb0-123">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="2adb0-124">**My Domains (내 도메인** ) 페이지의 **고급** 영역에서 **DNS 편집** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-124">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="2adb0-125">DNS 편집기의 **TXT (텍스트)** 행에서 **다른** 열을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-125">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="2adb0-126">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="2adb0-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="2adb0-127">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="2adb0-127">**Host Name**</span></span> <br/> |<span data-ttu-id="2adb0-128">**TXT VALUE(TXT 값)**</span><span class="sxs-lookup"><span data-stu-id="2adb0-128">**TXT Value**</span></span> <br/> |<span data-ttu-id="2adb0-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2adb0-129">**TTL**</span></span> <br/> |
|<span data-ttu-id="2adb0-130">자동으로 채워짐</span><span class="sxs-lookup"><span data-stu-id="2adb0-130">Automatically populated</span></span>  <br/> |<span data-ttu-id="2adb0-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="2adb0-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="2adb0-132">**참고:** 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-132">**Note:** This is an example.</span></span> <span data-ttu-id="2adb0-133">여기에는 Office 365의 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-133">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>  [<span data-ttu-id="2adb0-134">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="2adb0-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="2adb0-135">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2adb0-135">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="2adb0-136">DNS 편집기 위쪽에 있는 **Dns 저장** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-136">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="2adb0-137">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="2adb0-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="2adb0-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="2adb0-139">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="2adb0-139">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="2adb0-140">관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="2adb0-141">**도메인** 페이지에서 확인 하려는 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
  
3. <span data-ttu-id="2adb0-142">**설정** 페이지에서 **설정 시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-142">On the **Setup** page, select **Start setup**.</span></span>
   
  
4. <span data-ttu-id="2adb0-143">**도메인 확인** 페이지에서 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="2adb0-p106">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2adb0-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="2adb0-147">사용자 도메인의 전자 메일이 Office 365로 전송되도록 MX 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="2adb0-147">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="2adb0-148"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="2adb0-148"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="2adb0-149">시작 하려면 [이 링크](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)를 사용 하 여 Wix의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-149">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="2adb0-150">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="2adb0-150">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="2adb0-151">**My Domains (내 도메인** ) 페이지의 **사서함** 영역에서 **MX 레코드 구성** 링크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-151">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="2adb0-152">**전자 메일 공급자** 드롭다운 목록에서 **기타** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-152">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="2adb0-153">**+ 다른 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-153">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="2adb0-154">새 레코드의 상자에서 다음 표의 값을 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-154">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="2adb0-155">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="2adb0-155">**Host Name**</span></span>|<span data-ttu-id="2adb0-156">**연결 대상**</span><span class="sxs-lookup"><span data-stu-id="2adb0-156">**Points to**</span></span>|<span data-ttu-id="2adb0-157">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="2adb0-157">**Priority**</span></span>|<span data-ttu-id="2adb0-158">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2adb0-158">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2adb0-159">자동으로 채워짐</span><span class="sxs-lookup"><span data-stu-id="2adb0-159">Automatically populated</span></span> <br/> | <span data-ttu-id="2adb0-160">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="2adb0-160">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="2adb0-161">**참고:** Office 365 계정에서 \* \<도메인\> 키\* 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-161">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="2adb0-162">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="2adb0-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="2adb0-163">개</span><span class="sxs-lookup"><span data-stu-id="2adb0-163">0</span></span>  <br/> <span data-ttu-id="2adb0-164">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/What-is-MX-priority-2784cc4d-95be-443d-b5f7-bb5dd867ba83)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2adb0-164">For more information about priority, see [What is MX priority?](https://support.office.com/article/What-is-MX-priority-2784cc4d-95be-443d-b5f7-bb5dd867ba83)</span></span> | <span data-ttu-id="2adb0-165">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2adb0-165">1 Hour</span></span>|
   
6. <span data-ttu-id="2adb0-166">다른 MX 레코드가 나열 되어 있는 경우 각 레코드를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-166">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="2adb0-167">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-167">Select **OK**.</span></span>
    
8. <span data-ttu-id="2adb0-168">확인 대화 상자에서 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-168">In the confirmation dialog box, select **OK**.</span></span>
    
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="2adb0-169">Office 365에 필요한 다섯 개의 CNAME 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-169">Add the five CNAME records that are required for Office 365</span></span>
<span data-ttu-id="2adb0-170"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="2adb0-170"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="2adb0-171">시작 하려면 [이 링크](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)를 사용 하 여 Wix의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-171">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="2adb0-172">You'll be prompted to login first.</span><span class="sxs-lookup"><span data-stu-id="2adb0-172">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="2adb0-173">**My Domains (내 도메인** ) 페이지의 **고급** 영역에서 **DNS 편집** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-173">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="2adb0-174">각 CNAME 레코드에 대 한 DNS 편집기의 **cname (별칭)** 행에서 다른 열로 **추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-174">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="2adb0-175">새 레코드의 상자에서 다음 표의 값을 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-175">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="2adb0-176">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="2adb0-176">**Host Name**</span></span>|<span data-ttu-id="2adb0-177">**연결 대상**</span><span class="sxs-lookup"><span data-stu-id="2adb0-177">**Points to**</span></span>|<span data-ttu-id="2adb0-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2adb0-178">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2adb0-179">autodiscover</span><span class="sxs-lookup"><span data-stu-id="2adb0-179">autodiscover</span></span>  <br/> |<span data-ttu-id="2adb0-180">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="2adb0-180">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="2adb0-181">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2adb0-181">1 Hour</span></span>  <br/> |
|<span data-ttu-id="2adb0-182">sip</span><span class="sxs-lookup"><span data-stu-id="2adb0-182">sip</span></span>  <br/> |<span data-ttu-id="2adb0-183">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2adb0-183">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="2adb0-184">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2adb0-184">1 Hour</span></span> <br/> |
|<span data-ttu-id="2adb0-185">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="2adb0-185">lyncdiscover</span></span>  <br/> |<span data-ttu-id="2adb0-186">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2adb0-186">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="2adb0-187">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2adb0-187">1 Hour</span></span>  <br/> |
|<span data-ttu-id="2adb0-188">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="2adb0-188">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="2adb0-189">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="2adb0-189">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="2adb0-190">1시간</span><span class="sxs-lookup"><span data-stu-id="2adb0-190">1 Hour</span></span> <br/> |
|<span data-ttu-id="2adb0-191">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="2adb0-191">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="2adb0-192">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="2adb0-192">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="2adb0-193">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2adb0-193">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="2adb0-194">DNS 편집기 위쪽에 있는 **Dns 저장** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-194">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="2adb0-195">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span><span class="sxs-lookup"><span data-stu-id="2adb0-195">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="2adb0-196">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="2adb0-196">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="2adb0-197"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="2adb0-197"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="2adb0-198">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="2adb0-198">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="2adb0-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="2adb0-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="2adb0-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="2adb0-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="2adb0-201">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="2adb0-201">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="2adb0-202">시작 하려면 [이 링크](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)를 사용 하 여 Wix의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-202">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="2adb0-203">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="2adb0-203">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="2adb0-204">**My Domains (내 도메인** ) 페이지의 **고급** 영역에서 **DNS 편집** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-204">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="2adb0-205">DNS 편집기의 **TXT (텍스트)** 행에서 **다른** 열을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-205">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="2adb0-206">새 레코드의 상자에서 다음 표의 값을 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-206">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="2adb0-207">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="2adb0-207">**Host Name**</span></span>|<span data-ttu-id="2adb0-208">**TXT VALUE(TXT 값)**</span><span class="sxs-lookup"><span data-stu-id="2adb0-208">**TXT Value**</span></span>|<span data-ttu-id="2adb0-209">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2adb0-209">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2adb0-210">[이 값을 비워 둠]</span><span class="sxs-lookup"><span data-stu-id="2adb0-210">[leave this blank]</span></span>  <br/> |<span data-ttu-id="2adb0-211">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="2adb0-211">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="2adb0-212">**참고:** 모든 공백이 올바르게 유지 되도록이 항목을 복사 하 여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-212">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="2adb0-213">TXT</span><span class="sxs-lookup"><span data-stu-id="2adb0-213">TXT</span></span>  <br/> | <span data-ttu-id="2adb0-214">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2adb0-214">1 Hour</span></span> |
   
5. <span data-ttu-id="2adb0-215">DNS 편집기 위쪽에 있는 **Dns 저장** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-215">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="2adb0-216">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span><span class="sxs-lookup"><span data-stu-id="2adb0-216">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="2adb0-217">Office 365에 필요한 2개의 SRV 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="2adb0-217">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="2adb0-218"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="2adb0-218"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="2adb0-219">시작 하려면 [이 링크](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)를 사용 하 여 Wix의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-219">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="2adb0-220">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="2adb0-220">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="2adb0-221">**My Domains (내 도메인** ) 페이지의 **고급** 영역에서 **DNS 편집** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-221">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="2adb0-222">DNS 편집기의 **SRV** 행에서 **다른 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-222">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="2adb0-223">새 레코드의 상자에서 다음 표의 값을 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-223">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="2adb0-224">**서비스**</span><span class="sxs-lookup"><span data-stu-id="2adb0-224">**Service**</span></span>|<span data-ttu-id="2adb0-225">**프로토콜**</span><span class="sxs-lookup"><span data-stu-id="2adb0-225">**Protocol**</span></span>|<span data-ttu-id="2adb0-226">**이름**</span><span class="sxs-lookup"><span data-stu-id="2adb0-226">**Name**</span></span>|<span data-ttu-id="2adb0-227">**가중치**</span><span class="sxs-lookup"><span data-stu-id="2adb0-227">**Weight**</span></span>|<span data-ttu-id="2adb0-228">**포트**</span><span class="sxs-lookup"><span data-stu-id="2adb0-228">**Port**</span></span>|<span data-ttu-id="2adb0-229">**대상**</span><span class="sxs-lookup"><span data-stu-id="2adb0-229">**Target**</span></span>|<span data-ttu-id="2adb0-230">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="2adb0-230">**Priority**</span></span>|<span data-ttu-id="2adb0-231">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2adb0-231">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2adb0-232">sip</span><span class="sxs-lookup"><span data-stu-id="2adb0-232">sip</span></span>  |<span data-ttu-id="2adb0-233">tls</span><span class="sxs-lookup"><span data-stu-id="2adb0-233">tls</span></span>  |<span data-ttu-id="2adb0-234">자동으로 채워짐</span><span class="sxs-lookup"><span data-stu-id="2adb0-234">Automatically populated</span></span> |<span data-ttu-id="2adb0-235">개</span><span class="sxs-lookup"><span data-stu-id="2adb0-235">1</span></span>  |<span data-ttu-id="2adb0-236">443</span><span class="sxs-lookup"><span data-stu-id="2adb0-236">443</span></span>   |<span data-ttu-id="2adb0-237">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2adb0-237">sipdir.online.lync.com</span></span> |<span data-ttu-id="2adb0-238">100</span><span class="sxs-lookup"><span data-stu-id="2adb0-238">100</span></span> |<span data-ttu-id="2adb0-239">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2adb0-239">1 Hour</span></span> |
|<span data-ttu-id="2adb0-240">sipfed.online.lync.com></span><span class="sxs-lookup"><span data-stu-id="2adb0-240">sipfed</span></span>|<span data-ttu-id="2adb0-241">tcp</span><span class="sxs-lookup"><span data-stu-id="2adb0-241">tcp</span></span> |<span data-ttu-id="2adb0-242">자동으로 채워짐</span><span class="sxs-lookup"><span data-stu-id="2adb0-242">Automatically populated</span></span>|<span data-ttu-id="2adb0-243">개</span><span class="sxs-lookup"><span data-stu-id="2adb0-243">1</span></span> |<span data-ttu-id="2adb0-244">5061</span><span class="sxs-lookup"><span data-stu-id="2adb0-244">5061</span></span> |<span data-ttu-id="2adb0-245">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2adb0-245">sipfed.online.lync.com</span></span>|<span data-ttu-id="2adb0-246">100</span><span class="sxs-lookup"><span data-stu-id="2adb0-246">100</span></span> | <span data-ttu-id="2adb0-247">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2adb0-247">1 Hour</span></span> |
   
5. <span data-ttu-id="2adb0-248">DNS 편집기 위쪽에 있는 **Dns 저장** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2adb0-248">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="2adb0-249">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span><span class="sxs-lookup"><span data-stu-id="2adb0-249">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="2adb0-p113">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2adb0-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

