---
title: OVH에서 Office 365에 대 한 DNS 레코드 만들기
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대 한 DNS 레코드를 Office 365 용 OVH에 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 87de24fd47ce048cb88a2b7d4bcff97b1c155456
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42248967"
---
# <a name="create-dns-records-at-ovh-for-office-365"></a><span data-ttu-id="10b85-103">OVH에서 Office 365에 대 한 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="10b85-103">Create DNS records at OVH for Office 365</span></span>

<span data-ttu-id="10b85-104">원하는 정보를 찾지 못한 경우 [도메인 FAQ를 확인](../setup/domains-faq.md)하세요.</span><span class="sxs-lookup"><span data-stu-id="10b85-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="10b85-105">OVH이 DNS 호스팅 공급자 인 경우이 문서의 단계에 따라 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 등에 대 한 DNS 레코드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-105">If OVH is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="10b85-106">다음은 추가할 기본 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="10b85-107">OVH에서 Office 365에 대 한 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="10b85-107">Create DNS records at OVH for Office 365</span></span>](#create-dns-records-at-ovh-for-office-365)
    
- [<span data-ttu-id="10b85-108">사용자 도메인의 전자 메일이 Office 365로 전송되도록 MX 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="10b85-108">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="10b85-109">Office 365에 필요한 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="10b85-109">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="10b85-110">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="10b85-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="10b85-111">Office 365에 필요한 2개의 SRV 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="10b85-111">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="10b85-112">OVH에서 이러한 레코드를 추가 하 고 나면 도메인이 Office 365 서비스에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-112">After you add these records at OVH, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="10b85-113">Office 365에서 웹 사이트의 웹 호스팅 및 DNS에 대한 자세한 내용은 [Office 365에서 공개 웹 사이트 사용](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="10b85-113">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="10b85-p101">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="10b85-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="10b85-117">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="10b85-117">Add a TXT record for verification</span></span>
<span data-ttu-id="10b85-118"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="10b85-118"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="10b85-p102">Office 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Office 365에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="10b85-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="10b85-123">시작 하려면 [이 링크](https://www.ovh.com/manager/)를 사용 하 여 OVH의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-123">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="10b85-124">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="10b85-124">You'll be prompted to log in.</span></span>
    
    ![OVH 로그인](../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="10b85-126">**도메인**에서 편집 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-126">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![도메인 OVH 선택](../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="10b85-128">**DNS 영역**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-128">Select **DNS zone**.</span></span>
    
    ![OVH select DNS 영역](../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="10b85-130">**항목 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-130">Select **Add an entry**.</span></span>
    
    ![OVH 항목 추가](../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="10b85-132">**TXT** 선택</span><span class="sxs-lookup"><span data-stu-id="10b85-132">Select **TXT**</span></span>
    
    ![OVH TXT 항목 선택](../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. <span data-ttu-id="10b85-134">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="10b85-134">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="10b85-135">TTL 값을 할당 하려면 드롭다운 목록에서 **개인 설정** 을 선택한 다음 텍스트 상자에 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-135">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="10b85-136">**Record type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="10b85-136">**Record type**</span></span>|<span data-ttu-id="10b85-137">**하위 도메인**</span><span class="sxs-lookup"><span data-stu-id="10b85-137">**Sub-domain**</span></span>|<span data-ttu-id="10b85-138">**TTL**</span><span class="sxs-lookup"><span data-stu-id="10b85-138">**TTL**</span></span>|<span data-ttu-id="10b85-139">**값**</span><span class="sxs-lookup"><span data-stu-id="10b85-139">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="10b85-140">TXT</span><span class="sxs-lookup"><span data-stu-id="10b85-140">TXT</span></span>  <br/> |<span data-ttu-id="10b85-141">(공백으로 둠)</span><span class="sxs-lookup"><span data-stu-id="10b85-141">(leave blank)</span></span>  <br/> |<span data-ttu-id="10b85-142">3600 (초)</span><span class="sxs-lookup"><span data-stu-id="10b85-142">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="10b85-143">MS = msxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="10b85-143">MS=msxxxxxxxx</span></span>  <br/> <span data-ttu-id="10b85-144">**참고:** 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-144">**Note:** This is an example.</span></span> <span data-ttu-id="10b85-145">여기에는 Office 365의 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-145">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="10b85-146">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="10b85-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="10b85-147">**확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-147">Select **Confirm**.</span></span> 
    
    ![확인을 위해 TXT 확인 OVH](../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. <span data-ttu-id="10b85-149">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-149">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="10b85-150">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="10b85-150">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="10b85-151">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="10b85-151">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="10b85-152">관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-152">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="10b85-153">**도메인** 페이지에서 확인 하려는 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-153">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="10b85-154">**설정** 페이지에서 **설정 시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-154">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="10b85-155">**도메인 확인** 페이지에서 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-155">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="10b85-p107">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="10b85-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="10b85-159">사용자 도메인의 전자 메일이 Office 365로 전송되도록 MX 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="10b85-159">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="10b85-160"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="10b85-160"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="10b85-161">시작 하려면 [이 링크](https://www.ovh.com/manager/)를 사용 하 여 OVH의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-161">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="10b85-162">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="10b85-162">You'll be prompted to log in.</span></span>
    
    ![OVH 로그인](../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="10b85-164">**도메인**에서 편집 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-164">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![도메인 OVH 선택](../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="10b85-166">**DNS 영역**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-166">Select **DNS zone**.</span></span>
    
    ![OVH select DNS 영역](../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="10b85-168">**항목 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-168">Select **Add an entry**.</span></span>
    
    ![OVH 항목 추가](../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="10b85-170">**MX**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-170">Select **MX**.</span></span>
    
    ![OVH MX 레코드 종류](../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. <span data-ttu-id="10b85-172">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="10b85-172">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="10b85-173">TTL 값을 할당 하려면 드롭다운 목록에서 **개인 설정** 을 선택한 다음 텍스트 상자에 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-173">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="10b85-174">기본적으로 OVH는 대상 레코드의 끝에 도메인 이름을 추가 하는 상대 표기법을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-174">By default OVH uses relative notation for the target, which adds the domain name to the end of the target record.</span></span> <span data-ttu-id="10b85-175">절대 표기법을 사용 하려면 아래 표에 나와 있는 것 처럼 대상 레코드에 점을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-175">To use absolute notation instead, add a dot to the target record as shown in the table below.</span></span> 
  
    |<span data-ttu-id="10b85-176">**Record type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="10b85-176">**Record type**</span></span>|<span data-ttu-id="10b85-177">**하위 도메인**</span><span class="sxs-lookup"><span data-stu-id="10b85-177">**Sub-domain**</span></span>|<span data-ttu-id="10b85-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="10b85-178">**TTL**</span></span>|<span data-ttu-id="10b85-179">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="10b85-179">**Priority**</span></span>|<span data-ttu-id="10b85-180">**대상**</span><span class="sxs-lookup"><span data-stu-id="10b85-180">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="10b85-181">MX</span><span class="sxs-lookup"><span data-stu-id="10b85-181">MX</span></span>  <br/> |<span data-ttu-id="10b85-182">(공백으로 둠)</span><span class="sxs-lookup"><span data-stu-id="10b85-182">(leave blank)</span></span>  <br/> |<span data-ttu-id="10b85-183">3600 (초)</span><span class="sxs-lookup"><span data-stu-id="10b85-183">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="10b85-184">10 </span><span class="sxs-lookup"><span data-stu-id="10b85-184">10</span></span>  <br/> <span data-ttu-id="10b85-185">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="10b85-185">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="10b85-186">\<mail.protection.outlook.com를 사용\>합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-186">\<domain-key\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="10b85-187">**참고:** Office 365 계정에서 \* \<도메인\> 키\* 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-187">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="10b85-188">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="10b85-188">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![메일에 대 한 OVH MX 레코드](../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. <span data-ttu-id="10b85-190"> Select **Next**. </span><span class="sxs-lookup"><span data-stu-id="10b85-190">Select **Next**.</span></span>
    
    ![OVH MX 레코드 다음 선택](../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. <span data-ttu-id="10b85-192">**확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-192">Select **Confirm**.</span></span>
    
    ![OVH MX 레코드 선택 확인](../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. <span data-ttu-id="10b85-194">다른 MX 레코드가 있으면 **DNS 영역** 페이지의 목록에서 모두 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-194">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span></span> <span data-ttu-id="10b85-195">각 레코드를 선택 하 고 **작업** 열에서 휴지통 **삭제** 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-195">Select each record and then, in the **Actions** column, select the trash-can **Delete** icon.</span></span> 
    
    ![OVH MX 레코드 삭제](../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. <span data-ttu-id="10b85-197">**확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-197">Select **Confirm**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="10b85-198">Office 365에 필요한 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="10b85-198">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="10b85-199"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="10b85-199"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="10b85-200">시작 하려면 [이 링크](https://www.ovh.com/manager/)를 사용 하 여 OVH의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-200">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="10b85-201">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="10b85-201">You'll be prompted to log in.</span></span>
    
    ![OVH 로그인](../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="10b85-203">**도메인**에서 편집 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-203">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![도메인 OVH 선택](../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="10b85-205">**DNS 영역**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-205">Select **DNS zone**.</span></span>
    
    ![OVH select DNS 영역](../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="10b85-207">**항목 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-207">Select **Add an entry**.</span></span>
    
    ![OVH 항목 추가](../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="10b85-209">**CNAME**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-209">Select **CNAME**.</span></span>
    
    ![OVH CNAME 레코드 종류 추가](../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. <span data-ttu-id="10b85-211">첫 번째 CNAME 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-211">Create the first CNAME record.</span></span>
    
    <span data-ttu-id="10b85-212">새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-212">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="10b85-213">TTL 값을 할당 하려면 드롭다운 목록에서 **개인 설정** 을 선택한 다음 텍스트 상자에 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-213">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="10b85-214">**Record type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="10b85-214">**Record type**</span></span>|<span data-ttu-id="10b85-215">**하위 도메인**</span><span class="sxs-lookup"><span data-stu-id="10b85-215">**Sub-domain**</span></span>|<span data-ttu-id="10b85-216">**대상**</span><span class="sxs-lookup"><span data-stu-id="10b85-216">**Target**</span></span>|<span data-ttu-id="10b85-217">**TTL**</span><span class="sxs-lookup"><span data-stu-id="10b85-217">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="10b85-218">CNAME</span><span class="sxs-lookup"><span data-stu-id="10b85-218">CNAME</span></span>  <br/> |<span data-ttu-id="10b85-219">autodiscover</span><span class="sxs-lookup"><span data-stu-id="10b85-219">autodiscover</span></span>  <br/> |<span data-ttu-id="10b85-220">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="10b85-220">autodiscover.outlook.com.</span></span>  <br/> |<span data-ttu-id="10b85-221">3600 초</span><span class="sxs-lookup"><span data-stu-id="10b85-221">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="10b85-222">CNAME</span><span class="sxs-lookup"><span data-stu-id="10b85-222">CNAME</span></span>  <br/> |<span data-ttu-id="10b85-223">sip</span><span class="sxs-lookup"><span data-stu-id="10b85-223">sip</span></span>  <br/> |<span data-ttu-id="10b85-224">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="10b85-224">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="10b85-225">3600 초</span><span class="sxs-lookup"><span data-stu-id="10b85-225">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="10b85-226">CNAME</span><span class="sxs-lookup"><span data-stu-id="10b85-226">CNAME</span></span>  <br/> |<span data-ttu-id="10b85-227">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="10b85-227">lyncdiscover</span></span>  <br/> |<span data-ttu-id="10b85-228">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="10b85-228">webdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="10b85-229">3600 초</span><span class="sxs-lookup"><span data-stu-id="10b85-229">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="10b85-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="10b85-230">CNAME</span></span>  <br/> |<span data-ttu-id="10b85-231">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="10b85-231">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="10b85-232">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="10b85-232">enterpriseregistration.windows.net.</span></span>  <br/> |<span data-ttu-id="10b85-233">3600 초</span><span class="sxs-lookup"><span data-stu-id="10b85-233">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="10b85-234">CNAME</span><span class="sxs-lookup"><span data-stu-id="10b85-234">CNAME</span></span>  <br/> |<span data-ttu-id="10b85-235">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="10b85-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="10b85-236">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="10b85-236">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |<span data-ttu-id="10b85-237">3600 초</span><span class="sxs-lookup"><span data-stu-id="10b85-237">3600 seconds</span></span>  <br/> |
   
    ![OVH CNAME 레코드](../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. <span data-ttu-id="10b85-239"> Select **Next**. </span><span class="sxs-lookup"><span data-stu-id="10b85-239">Select **Next**.</span></span>
    
    ![OVH CNAME 값을 추가 하 고 다음을 선택 합니다.](../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. <span data-ttu-id="10b85-241">**확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-241">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="10b85-242">이전 단계를 반복 하 여 나머지 5 개의 CNAME 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-242">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="10b85-243">각 레코드에 대해 위 표에 있는 다음 행의 값을 해당 레코드의 상자에 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-243">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="10b85-244">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="10b85-244">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="10b85-245"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="10b85-245"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="10b85-246">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="10b85-246">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="10b85-247">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="10b85-247">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="10b85-248">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="10b85-248">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="10b85-249">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="10b85-249">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="10b85-250">시작 하려면 [이 링크](https://www.ovh.com/manager/)를 사용 하 여 OVH의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-250">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="10b85-251">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="10b85-251">You'll be prompted to log in.</span></span>
    
    ![OVH 로그인](../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="10b85-253">**도메인**에서 편집 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-253">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![도메인 OVH 선택](../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="10b85-255">**DNS 영역**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-255">Select **DNS zone**.</span></span>
    
    ![OVH select DNS 영역](../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="10b85-257">**항목 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-257">Select **Add an entry**.</span></span>
    
    ![OVH 항목 추가](../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="10b85-259">**TXT**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-259">Select **TXT**.</span></span>
    
6. <span data-ttu-id="10b85-260">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="10b85-260">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="10b85-261">**Record type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="10b85-261">**Record type**</span></span>|<span data-ttu-id="10b85-262">**하위 도메인**</span><span class="sxs-lookup"><span data-stu-id="10b85-262">**Sub-domain**</span></span>|<span data-ttu-id="10b85-263">**TTL**</span><span class="sxs-lookup"><span data-stu-id="10b85-263">**TTL**</span></span>|<span data-ttu-id="10b85-264">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="10b85-264">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="10b85-265">TXT</span><span class="sxs-lookup"><span data-stu-id="10b85-265">TXT</span></span>  <br/> |<span data-ttu-id="10b85-266">(공백으로 둠)</span><span class="sxs-lookup"><span data-stu-id="10b85-266">(leave blank)</span></span>  <br/> |<span data-ttu-id="10b85-267">3600 (초)</span><span class="sxs-lookup"><span data-stu-id="10b85-267">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="10b85-268">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="10b85-268">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="10b85-269">**참고:** 모든 공백이 올바르게 유지 되도록이 항목을 복사 하 여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![SPF에 대 한 OVH 추가 TXT 레코드](../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. <span data-ttu-id="10b85-271"> Select **Next**. </span><span class="sxs-lookup"><span data-stu-id="10b85-271">Select **Next**.</span></span>
    
    ![SPF 용 TXT 레코드 추가 OVH 및 다음 선택](../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. <span data-ttu-id="10b85-273">**확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-273">Select **Confirm**.</span></span>
    
    ![SPF 및 확인을 위한 OVH 추가 TXT 레코드](../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="10b85-275">Office 365에 필요한 2개의 SRV 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="10b85-275">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="10b85-276"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="10b85-276"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="10b85-277">시작 하려면 [이 링크](https://www.ovh.com/manager/)를 사용 하 여 OVH의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-277">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="10b85-278">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="10b85-278">You'll be prompted to log in.</span></span>
    
    ![OVH 로그인](../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="10b85-280">**도메인**에서 편집 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-280">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![도메인 OVH 선택](../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="10b85-282">**DNS 영역**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-282">Select **DNS zone**.</span></span>
    
    ![OVH select DNS 영역](../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="10b85-284">**항목 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-284">Select **Add an entry**.</span></span>
    
    ![OVH 항목 추가](../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="10b85-286">**SRV**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-286">Select **SRV**.</span></span>
    
    ![OVH select SRV 레코드 유형](../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. <span data-ttu-id="10b85-288">첫 번째 SRV 레코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-288">Create the first SRV record.</span></span>
    
    <span data-ttu-id="10b85-289">새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-289">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="10b85-290">TTL 값을 할당 하려면 드롭다운 목록에서 **개인 설정** 을 선택한 다음 텍스트 상자에 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-290">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="10b85-291">**Record type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="10b85-291">**Record type**</span></span>|<span data-ttu-id="10b85-292">**하위 도메인**</span><span class="sxs-lookup"><span data-stu-id="10b85-292">**Sub-domain**</span></span>|<span data-ttu-id="10b85-293">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="10b85-293">**Priority**</span></span>|<span data-ttu-id="10b85-294">**가중치**</span><span class="sxs-lookup"><span data-stu-id="10b85-294">**Weight**</span></span>|<span data-ttu-id="10b85-295">**포트**</span><span class="sxs-lookup"><span data-stu-id="10b85-295">**Port**</span></span>|<span data-ttu-id="10b85-296">**TTL**</span><span class="sxs-lookup"><span data-stu-id="10b85-296">**TTL**</span></span>|<span data-ttu-id="10b85-297">**대상**</span><span class="sxs-lookup"><span data-stu-id="10b85-297">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="10b85-298">SRV (Service)(SRV(서비스))</span><span class="sxs-lookup"><span data-stu-id="10b85-298">SRV (Service)</span></span>  <br/> |<span data-ttu-id="10b85-299">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="10b85-299">_sip._tls</span></span>  <br/> |<span data-ttu-id="10b85-300">100</span><span class="sxs-lookup"><span data-stu-id="10b85-300">100</span></span>  <br/> |<span data-ttu-id="10b85-301">개</span><span class="sxs-lookup"><span data-stu-id="10b85-301">1</span></span>  <br/> |<span data-ttu-id="10b85-302">443</span><span class="sxs-lookup"><span data-stu-id="10b85-302">443</span></span>  <br/> |<span data-ttu-id="10b85-303">3600 (초)</span><span class="sxs-lookup"><span data-stu-id="10b85-303">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="10b85-304">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="10b85-304">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="10b85-305">SRV (Service)(SRV(서비스))</span><span class="sxs-lookup"><span data-stu-id="10b85-305">SRV (Service)</span></span>  <br/> |<span data-ttu-id="10b85-306">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="10b85-306">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="10b85-307">100</span><span class="sxs-lookup"><span data-stu-id="10b85-307">100</span></span>  <br/> |<span data-ttu-id="10b85-308">개</span><span class="sxs-lookup"><span data-stu-id="10b85-308">1</span></span>  <br/> |<span data-ttu-id="10b85-309">5061</span><span class="sxs-lookup"><span data-stu-id="10b85-309">5061</span></span>  <br/> |<span data-ttu-id="10b85-310">3600 (초)</span><span class="sxs-lookup"><span data-stu-id="10b85-310">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="10b85-311">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="10b85-311">sipfed.online.lync.com.</span></span>  <br/> |
       
    ![OVH SRV 레코드](../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. <span data-ttu-id="10b85-313"> Select **Next**. </span><span class="sxs-lookup"><span data-stu-id="10b85-313">Select **Next**.</span></span>
    
    ![OVH SRV 레코드 다음 선택](../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. <span data-ttu-id="10b85-315">**확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-315">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="10b85-316">이전 단계를 반복 하 여 다른 SRV 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-316">Repeat the previous steps to create the other SRV record.</span></span> <span data-ttu-id="10b85-317">위 표에 있는 두 번째 행의 값을 두 번째 레코드의 상자에 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="10b85-317">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="10b85-p120">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="10b85-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
