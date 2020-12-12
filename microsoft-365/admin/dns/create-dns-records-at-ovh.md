---
title: Microsoft용 OVH에서 DNS 레코드 만들기
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: Microsoft용 OVH에서 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대한 DNS 레코드를 설정하는 방법을 학습합니다.
ms.openlocfilehash: 14c3796ff6686ae0d98ec32ec6ddf6afc004a3c3
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657782"
---
# <a name="create-dns-records-at-ovh-for-microsoft"></a><span data-ttu-id="01eae-103">Microsoft용 OVH에서 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="01eae-103">Create DNS records at OVH for Microsoft</span></span>

<span data-ttu-id="01eae-104">원하는 정보를 찾지 못한 경우 [도메인 FAQ를 확인](../setup/domains-faq.yml)하세요.</span><span class="sxs-lookup"><span data-stu-id="01eae-104">[Check the Domains FAQ](../setup/domains-faq.yml) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="01eae-105">DNS 호스팅 공급자로 OVH를 사용하고 있는 경우 이 문서의 단계에 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online에 대한 DNS 레코드를 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="01eae-105">If OVH is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="01eae-106">다음은 추가할 기본 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="01eae-107">Microsoft용 OVH에서 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="01eae-107">Create DNS records at OVH for Microsoft</span></span>](#create-dns-records-at-ovh-for-microsoft)
    
- [<span data-ttu-id="01eae-108">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="01eae-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="01eae-109">Microsoft에 필요한 CNAME 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="01eae-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="01eae-110">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="01eae-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="01eae-111">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="01eae-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="01eae-112">OVH에서 이러한 레코드를 추가하고 나면 도메인이 Microsoft 서비스에서 작동할 수 있도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-112">After you add these records at OVH, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="01eae-p101">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="01eae-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="01eae-116">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="01eae-116">Add a TXT record for verification</span></span>
<span data-ttu-id="01eae-117"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="01eae-117"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="01eae-p102">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="01eae-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="01eae-122">시작하려면 이 링크를 사용하여 OVH의 도메인 [페이지로 이동합니다.](https://www.ovh.com/manager/)</span><span class="sxs-lookup"><span data-stu-id="01eae-122">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="01eae-123">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="01eae-123">You'll be prompted to log in.</span></span>
    
    ![OVH 로그인](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="01eae-125">**도메인에서** 편집할 도메인의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-125">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH 도메인 선택](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="01eae-127">**DNS 영역 선택.**</span><span class="sxs-lookup"><span data-stu-id="01eae-127">Select **DNS zone**.</span></span>
    
    ![OVH 선택 DNS 영역](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="01eae-129">항목 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="01eae-129">Select **Add an entry**.</span></span>
    
    ![OVH 항목 추가](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="01eae-131">**TXT 선택**</span><span class="sxs-lookup"><span data-stu-id="01eae-131">Select **TXT**</span></span>
    
    ![OVH 선택 TXT 항목](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. <span data-ttu-id="01eae-133">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-133">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="01eae-134">TTL 값을 할당하기  위해 드롭다운 목록에서 개인 설정 값을 선택한 다음 텍스트 상자에 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-134">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="01eae-135">**Record type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="01eae-135">**Record type**</span></span>|<span data-ttu-id="01eae-136">**하위 도메인**</span><span class="sxs-lookup"><span data-stu-id="01eae-136">**Sub-domain**</span></span>|<span data-ttu-id="01eae-137">**TTL**</span><span class="sxs-lookup"><span data-stu-id="01eae-137">**TTL**</span></span>|<span data-ttu-id="01eae-138">**값**</span><span class="sxs-lookup"><span data-stu-id="01eae-138">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="01eae-139">TXT</span><span class="sxs-lookup"><span data-stu-id="01eae-139">TXT</span></span>  <br/> |<span data-ttu-id="01eae-140">(공백으로 둠)</span><span class="sxs-lookup"><span data-stu-id="01eae-140">(leave blank)</span></span>  <br/> |<span data-ttu-id="01eae-141">3600(초)</span><span class="sxs-lookup"><span data-stu-id="01eae-141">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="01eae-142">MS=msxxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="01eae-142">MS=msxxxxxxxx</span></span>  <br/> <span data-ttu-id="01eae-143">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-143">**Note:** This is an example.</span></span> <span data-ttu-id="01eae-144">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-144">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="01eae-145">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="01eae-145">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="01eae-146">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-146">Select **Confirm**.</span></span> 
    
    ![OVH 확인을 위해 TXT 확인](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. <span data-ttu-id="01eae-148">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-148">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="01eae-149">이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-149">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="01eae-150">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-150">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="01eae-151">I관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인</a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="01eae-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="01eae-152">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="01eae-153">**설정** 페이지에서 **설정 시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="01eae-154">**도메인 확인** 페이지에서 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="01eae-p107">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="01eae-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="01eae-158">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="01eae-158">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="01eae-159"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="01eae-159"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="01eae-160">시작하려면 이 링크를 사용하여 OVH의 도메인 [페이지로 이동합니다.](https://www.ovh.com/manager/)</span><span class="sxs-lookup"><span data-stu-id="01eae-160">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="01eae-161">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="01eae-161">You'll be prompted to log in.</span></span>
    
    ![OVH 로그인](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="01eae-163">**도메인에서** 편집할 도메인의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-163">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH 도메인 선택](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="01eae-165">**DNS 영역 선택.**</span><span class="sxs-lookup"><span data-stu-id="01eae-165">Select **DNS zone**.</span></span>
    
    ![OVH 선택 DNS 영역](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="01eae-167">항목 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="01eae-167">Select **Add an entry**.</span></span>
    
    ![OVH 항목 추가](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="01eae-169">**MX를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="01eae-169">Select **MX**.</span></span>
    
    ![OVH MX 레코드 유형](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. <span data-ttu-id="01eae-171">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-171">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="01eae-172">TTL 값을 할당하기  위해 드롭다운 목록에서 개인 설정 값을 선택한 다음 텍스트 상자에 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-172">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="01eae-173">기본적으로 OVH는 대상에 대해 상대 표기 기능을 사용하여 대상 레코드의 끝에 도메인 이름을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-173">By default OVH uses relative notation for the target, which adds the domain name to the end of the target record.</span></span> <span data-ttu-id="01eae-174">대신 절대 표기 방법을 사용하세요. 아래 표와 같이 대상 레코드에 점을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-174">To use absolute notation instead, add a dot to the target record as shown in the table below.</span></span> 
  
    |<span data-ttu-id="01eae-175">**Record type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="01eae-175">**Record type**</span></span>|<span data-ttu-id="01eae-176">**하위 도메인**</span><span class="sxs-lookup"><span data-stu-id="01eae-176">**Sub-domain**</span></span>|<span data-ttu-id="01eae-177">**TTL**</span><span class="sxs-lookup"><span data-stu-id="01eae-177">**TTL**</span></span>|<span data-ttu-id="01eae-178">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="01eae-178">**Priority**</span></span>|<span data-ttu-id="01eae-179">**Target(대상)**</span><span class="sxs-lookup"><span data-stu-id="01eae-179">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="01eae-180">MX</span><span class="sxs-lookup"><span data-stu-id="01eae-180">MX</span></span>  <br/> |<span data-ttu-id="01eae-181">(공백으로 둠)</span><span class="sxs-lookup"><span data-stu-id="01eae-181">(leave blank)</span></span>  <br/> |<span data-ttu-id="01eae-182">3600(초)</span><span class="sxs-lookup"><span data-stu-id="01eae-182">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="01eae-183">10 </span><span class="sxs-lookup"><span data-stu-id="01eae-183">10</span></span>  <br/> <span data-ttu-id="01eae-184">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="01eae-184">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="01eae-185">\<domain-key\>.mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="01eae-185">\<domain-key\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="01eae-186">**참고:** Microsoft  *\<domain-key\>*  계정에서 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="01eae-186">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="01eae-187">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="01eae-187">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![메일에 대한 OVH MX 레코드](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. <span data-ttu-id="01eae-189">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-189">Select **Next**.</span></span>
    
    ![OVH MX 레코드 선택 다음](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. <span data-ttu-id="01eae-191">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-191">Select **Confirm**.</span></span>
    
    ![OVH MX 레코드 선택 확인](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. <span data-ttu-id="01eae-193">다른 MX 레코드가 있는 경우 DNS 영역 페이지의 목록에서 모두 **삭제합니다.**</span><span class="sxs-lookup"><span data-stu-id="01eae-193">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span></span> <span data-ttu-id="01eae-194">각 레코드를 선택한 다음  작업 열에서 휴지통 삭제 **아이콘을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-194">Select each record and then, in the **Actions** column, select the trash-can **Delete** icon.</span></span> 
    
    ![OVH 삭제 MX 레코드](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. <span data-ttu-id="01eae-196">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-196">Select **Confirm**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="01eae-197">Microsoft에 필요한 CNAME 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="01eae-197">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="01eae-198"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="01eae-198"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="01eae-199">시작하려면 이 링크를 사용하여 OVH의 도메인 [페이지로 이동합니다.](https://www.ovh.com/manager/)</span><span class="sxs-lookup"><span data-stu-id="01eae-199">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="01eae-200">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="01eae-200">You'll be prompted to log in.</span></span>
    
    ![OVH 로그인](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="01eae-202">**도메인에서** 편집할 도메인의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-202">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH 도메인 선택](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="01eae-204">**DNS 영역 선택.**</span><span class="sxs-lookup"><span data-stu-id="01eae-204">Select **DNS zone**.</span></span>
    
    ![OVH 선택 DNS 영역](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="01eae-206">항목 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="01eae-206">Select **Add an entry**.</span></span>
    
    ![OVH 항목 추가](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="01eae-208">**CNAME을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="01eae-208">Select **CNAME**.</span></span>
    
    ![OVH CNAME 레코드 유형 추가](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. <span data-ttu-id="01eae-210">첫 번째 CNAME 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-210">Create the first CNAME record.</span></span>
    
    <span data-ttu-id="01eae-211">새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-211">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="01eae-212">TTL 값을 할당하기  위해 드롭다운 목록에서 개인 설정 값을 선택한 다음 텍스트 상자에 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-212">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="01eae-213">**Record type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="01eae-213">**Record type**</span></span>|<span data-ttu-id="01eae-214">**하위 도메인**</span><span class="sxs-lookup"><span data-stu-id="01eae-214">**Sub-domain**</span></span>|<span data-ttu-id="01eae-215">**대상**</span><span class="sxs-lookup"><span data-stu-id="01eae-215">**Target**</span></span>|<span data-ttu-id="01eae-216">**TTL**</span><span class="sxs-lookup"><span data-stu-id="01eae-216">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="01eae-217">CNAME</span><span class="sxs-lookup"><span data-stu-id="01eae-217">CNAME</span></span>  <br/> |<span data-ttu-id="01eae-218">autodiscover</span><span class="sxs-lookup"><span data-stu-id="01eae-218">autodiscover</span></span>  <br/> |<span data-ttu-id="01eae-219">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="01eae-219">autodiscover.outlook.com.</span></span>  <br/> |<span data-ttu-id="01eae-220">3600초</span><span class="sxs-lookup"><span data-stu-id="01eae-220">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="01eae-221">CNAME</span><span class="sxs-lookup"><span data-stu-id="01eae-221">CNAME</span></span>  <br/> |<span data-ttu-id="01eae-222">sip</span><span class="sxs-lookup"><span data-stu-id="01eae-222">sip</span></span>  <br/> |<span data-ttu-id="01eae-223">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="01eae-223">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="01eae-224">3600초</span><span class="sxs-lookup"><span data-stu-id="01eae-224">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="01eae-225">CNAME</span><span class="sxs-lookup"><span data-stu-id="01eae-225">CNAME</span></span>  <br/> |<span data-ttu-id="01eae-226">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="01eae-226">lyncdiscover</span></span>  <br/> |<span data-ttu-id="01eae-227">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="01eae-227">webdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="01eae-228">3600초</span><span class="sxs-lookup"><span data-stu-id="01eae-228">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="01eae-229">CNAME</span><span class="sxs-lookup"><span data-stu-id="01eae-229">CNAME</span></span>  <br/> |<span data-ttu-id="01eae-230">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="01eae-230">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="01eae-231">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="01eae-231">enterpriseregistration.windows.net.</span></span>  <br/> |<span data-ttu-id="01eae-232">3600초</span><span class="sxs-lookup"><span data-stu-id="01eae-232">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="01eae-233">CNAME</span><span class="sxs-lookup"><span data-stu-id="01eae-233">CNAME</span></span>  <br/> |<span data-ttu-id="01eae-234">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="01eae-234">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="01eae-235">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="01eae-235">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |<span data-ttu-id="01eae-236">3600초</span><span class="sxs-lookup"><span data-stu-id="01eae-236">3600 seconds</span></span>  <br/> |
   
    ![OVH CNAME 레코드](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. <span data-ttu-id="01eae-238">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-238">Select **Next**.</span></span>
    
    ![OVH CNAME 값 추가 및 다음 선택](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. <span data-ttu-id="01eae-240">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-240">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="01eae-241">이전 단계를 반복하여 나머지 5개의 CNAME 레코드를 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="01eae-241">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="01eae-242">각 레코드에 대해 위 표의 다음 행 값을 해당 레코드의 상자에 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-242">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="01eae-243">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="01eae-243">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="01eae-244"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="01eae-244"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="01eae-245">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-245">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="01eae-246">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-246">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="01eae-247">도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="01eae-247">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="01eae-248">대신 두 값 집합을 모두 포함하는  *단일*  SPF 레코드가 있도록 현재 레코드에 필요한 Microsoft 값을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-248">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="01eae-249">시작하려면 이 링크를 사용하여 OVH의 도메인 [페이지로 이동합니다.](https://www.ovh.com/manager/)</span><span class="sxs-lookup"><span data-stu-id="01eae-249">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="01eae-250">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="01eae-250">You'll be prompted to log in.</span></span>
    
    ![OVH 로그인](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="01eae-252">**도메인에서** 편집할 도메인의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-252">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH 도메인 선택](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="01eae-254">**DNS 영역 선택.**</span><span class="sxs-lookup"><span data-stu-id="01eae-254">Select **DNS zone**.</span></span>
    
    ![OVH 선택 DNS 영역](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="01eae-256">항목 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="01eae-256">Select **Add an entry**.</span></span>
    
    ![OVH 항목 추가](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="01eae-258">**TXT를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="01eae-258">Select **TXT**.</span></span>
    
6. <span data-ttu-id="01eae-259">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="01eae-259">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="01eae-260">**Record type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="01eae-260">**Record type**</span></span>|<span data-ttu-id="01eae-261">**하위 도메인**</span><span class="sxs-lookup"><span data-stu-id="01eae-261">**Sub-domain**</span></span>|<span data-ttu-id="01eae-262">**TTL**</span><span class="sxs-lookup"><span data-stu-id="01eae-262">**TTL**</span></span>|<span data-ttu-id="01eae-263">**TXT 값**</span><span class="sxs-lookup"><span data-stu-id="01eae-263">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="01eae-264">TXT</span><span class="sxs-lookup"><span data-stu-id="01eae-264">TXT</span></span>  <br/> |<span data-ttu-id="01eae-265">(공백으로 둠)</span><span class="sxs-lookup"><span data-stu-id="01eae-265">(leave blank)</span></span>  <br/> |<span data-ttu-id="01eae-266">3600(초)</span><span class="sxs-lookup"><span data-stu-id="01eae-266">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="01eae-267">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="01eae-267">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="01eae-268">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-268">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![SPF에 대한 OVH TXT 레코드 추가](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. <span data-ttu-id="01eae-270">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-270">Select **Next**.</span></span>
    
    ![OVH SPF에 대한 TXT 레코드 추가 및 다음 선택](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. <span data-ttu-id="01eae-272">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-272">Select **Confirm**.</span></span>
    
    ![SPF 및 Confirm에 대한 OVH TXT 레코드 추가](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="01eae-274">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="01eae-274">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="01eae-275"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="01eae-275"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="01eae-276">시작하려면 이 링크를 사용하여 OVH의 도메인 [페이지로 이동합니다.](https://www.ovh.com/manager/)</span><span class="sxs-lookup"><span data-stu-id="01eae-276">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="01eae-277">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="01eae-277">You'll be prompted to log in.</span></span>
    
    ![OVH 로그인](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="01eae-279">**도메인에서** 편집할 도메인의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-279">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH 도메인 선택](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="01eae-281">**DNS 영역 선택.**</span><span class="sxs-lookup"><span data-stu-id="01eae-281">Select **DNS zone**.</span></span>
    
    ![OVH 선택 DNS 영역](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="01eae-283">항목 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="01eae-283">Select **Add an entry**.</span></span>
    
    ![OVH 항목 추가](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="01eae-285">**SRV를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="01eae-285">Select **SRV**.</span></span>
    
    ![OVH 선택 SRV 레코드 유형](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. <span data-ttu-id="01eae-287">첫 번째 SRV 레코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-287">Create the first SRV record.</span></span>
    
    <span data-ttu-id="01eae-288">새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-288">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="01eae-289">TTL 값을 할당하기  위해 드롭다운 목록에서 개인 설정 값을 선택한 다음 텍스트 상자에 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-289">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="01eae-290">**Record type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="01eae-290">**Record type**</span></span>|<span data-ttu-id="01eae-291">**하위 도메인**</span><span class="sxs-lookup"><span data-stu-id="01eae-291">**Sub-domain**</span></span>|<span data-ttu-id="01eae-292">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="01eae-292">**Priority**</span></span>|<span data-ttu-id="01eae-293">**Weight(가중치)**</span><span class="sxs-lookup"><span data-stu-id="01eae-293">**Weight**</span></span>|<span data-ttu-id="01eae-294">**Port(포트)**</span><span class="sxs-lookup"><span data-stu-id="01eae-294">**Port**</span></span>|<span data-ttu-id="01eae-295">**TTL**</span><span class="sxs-lookup"><span data-stu-id="01eae-295">**TTL**</span></span>|<span data-ttu-id="01eae-296">**Target(대상)**</span><span class="sxs-lookup"><span data-stu-id="01eae-296">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="01eae-297">SRV (Service)(SRV(서비스))</span><span class="sxs-lookup"><span data-stu-id="01eae-297">SRV (Service)</span></span>  <br/> |<span data-ttu-id="01eae-298">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="01eae-298">_sip._tls</span></span>  <br/> |<span data-ttu-id="01eae-299">100</span><span class="sxs-lookup"><span data-stu-id="01eae-299">100</span></span>  <br/> |<span data-ttu-id="01eae-300">1 </span><span class="sxs-lookup"><span data-stu-id="01eae-300">1</span></span>  <br/> |<span data-ttu-id="01eae-301">443</span><span class="sxs-lookup"><span data-stu-id="01eae-301">443</span></span>  <br/> |<span data-ttu-id="01eae-302">3600(초)</span><span class="sxs-lookup"><span data-stu-id="01eae-302">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="01eae-303">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="01eae-303">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="01eae-304">SRV (Service)(SRV(서비스))</span><span class="sxs-lookup"><span data-stu-id="01eae-304">SRV (Service)</span></span>  <br/> |<span data-ttu-id="01eae-305">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="01eae-305">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="01eae-306">100</span><span class="sxs-lookup"><span data-stu-id="01eae-306">100</span></span>  <br/> |<span data-ttu-id="01eae-307">1 </span><span class="sxs-lookup"><span data-stu-id="01eae-307">1</span></span>  <br/> |<span data-ttu-id="01eae-308">5061</span><span class="sxs-lookup"><span data-stu-id="01eae-308">5061</span></span>  <br/> |<span data-ttu-id="01eae-309">3600(초)</span><span class="sxs-lookup"><span data-stu-id="01eae-309">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="01eae-310">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="01eae-310">sipfed.online.lync.com.</span></span>  <br/> |
       
    ![OVH SRV 레코드](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. <span data-ttu-id="01eae-312">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-312">Select **Next**.</span></span>
    
    ![OVH SRV 레코드 선택 다음](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. <span data-ttu-id="01eae-314">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-314">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="01eae-315">이전 단계를 반복하여 다른 SRV 레코드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-315">Repeat the previous steps to create the other SRV record.</span></span> <span data-ttu-id="01eae-316">위 표에 있는 두 번째 행의 값을 두 번째 레코드의 상자에 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="01eae-316">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="01eae-p120">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="01eae-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
