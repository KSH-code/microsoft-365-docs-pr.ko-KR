---
title: Microsoft에 대 한 Freenom에서 DNS 레코드 만들기
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online에 대 한 DNS 레코드를 설정 하 고 Microsoft의 Freenom에 있는 기타 서비스를 설치 하는 방법을 알아봅니다.
ms.openlocfilehash: 39963b5c0f5f3f82fe193160e8aa8ab03894cedd
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049038"
---
# <a name="create-dns-records-at-freenom-for-microsoft"></a><span data-ttu-id="8f5ef-103">Microsoft에 대 한 Freenom에서 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="8f5ef-103">Create DNS records at Freenom for Microsoft</span></span>

<span data-ttu-id="8f5ef-104">원하는 정보를 찾지 못한 경우 [도메인 FAQ를 확인](../setup/domains-faq.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="8f5ef-105">Freenom 웹 사이트에서는 SRV 레코드를 지원 하지 않으므로 비즈니스용 Skype 온라인 및 Outlook Web App 기능이 여러 개 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-105">The Freenom website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="8f5ef-106">사용 하는 Microsoft 계획에 관계 없이 중요 한 서비스 제한이 있으며 다른 DNS 호스팅 공급자로 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-106">No matter which Microsoft plan you use, there are significant service limitations, and you may want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="8f5ef-107">서비스 제한 사항에도 불구 하 고 Freenom에서 자체 Microsoft DNS 레코드를 관리 하도록 선택 하는 경우이 문서의 단계에 따라 도메인을 확인 하 고 전자 메일 및 기타 서비스에 대 한 DNS 레코드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-107">If despite the service limitations, you choose to manage your own Microsoft DNS records at Freenom, follow the steps in this article to verify your domain and set up DNS records for email and other services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="8f5ef-p102">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="8f5ef-111">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="8f5ef-111">Add a TXT record for verification</span></span>
<span data-ttu-id="8f5ef-112"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="8f5ef-112"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="8f5ef-p103">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8f5ef-p104">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="8f5ef-117">시작 하려면 [이 링크](https://my.freenom.com/)를 사용 하 여 Freenom의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-117">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="8f5ef-118">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-118">You'll be prompted to log in.</span></span>
    
    ![Freenom 로그인](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="8f5ef-120">**서비스**를 선택한 다음 **내 도메인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-120">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom 서비스 및 내 도메인 선택](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="8f5ef-122">편집 하려는 도메인에서 **도메인 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-122">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom 관리 도메인 선택](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="8f5ef-124">**Freenom DNS 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-124">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom 관리 Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. <span data-ttu-id="8f5ef-126">**레코드 추가**의 **형식** 열에 있는 메뉴에서 **TXT** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-126">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom 레코드 형식 TXT 추가](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. <span data-ttu-id="8f5ef-128">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-128">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="8f5ef-129">**이름**</span><span class="sxs-lookup"><span data-stu-id="8f5ef-129">**Name**</span></span>|<span data-ttu-id="8f5ef-130">**종류**</span><span class="sxs-lookup"><span data-stu-id="8f5ef-130">**Type**</span></span>|<span data-ttu-id="8f5ef-131">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8f5ef-131">**TTL**</span></span>|<span data-ttu-id="8f5ef-132">**Target(대상)**</span><span class="sxs-lookup"><span data-stu-id="8f5ef-132">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8f5ef-133">(공백으로 둠)</span><span class="sxs-lookup"><span data-stu-id="8f5ef-133">(leave blank)</span></span>  <br/> |<span data-ttu-id="8f5ef-134">TXT</span><span class="sxs-lookup"><span data-stu-id="8f5ef-134">TXT</span></span>  <br/> |<span data-ttu-id="8f5ef-135">3600 (초)</span><span class="sxs-lookup"><span data-stu-id="8f5ef-135">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="8f5ef-136">MS = msXXXXXXXX</span><span class="sxs-lookup"><span data-stu-id="8f5ef-136">MS=msXXXXXXXX</span></span>  <br/> <span data-ttu-id="8f5ef-137">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-137">**Note:** This is an example.</span></span> <span data-ttu-id="8f5ef-138">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-138">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="8f5ef-139">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="8f5ef-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![확인을 위한 freenom TXT 값](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. <span data-ttu-id="8f5ef-141">**변경 내용 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-141">Select **Save Changes**.</span></span>
    
    ![Freenom TXT 레코드 저장 변경 내용](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. <span data-ttu-id="8f5ef-143">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-143">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="8f5ef-144">이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-144">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="8f5ef-145">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-145">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="8f5ef-146">Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-146">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="8f5ef-147">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="8f5ef-148">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="8f5ef-149">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="8f5ef-p107">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="8f5ef-153">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="8f5ef-153">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="8f5ef-154"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="8f5ef-154"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="8f5ef-155">시작 하려면 [이 링크](https://my.freenom.com/)를 사용 하 여 Freenom의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-155">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="8f5ef-156">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-156">You'll be prompted to log in.</span></span>
    
    ![Freenom 로그인](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="8f5ef-158">**서비스**를 선택한 다음 **내 도메인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-158">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom 서비스 및 내 도메인 선택](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="8f5ef-160">편집 하려는 도메인에서 **도메인 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-160">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom 관리 도메인 선택](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="8f5ef-162">도메인에 사용 되는 이름을 기본 Freenom 이름 서버로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-162">Set the name serves for your domain to the default Freenom name servers.</span></span> <span data-ttu-id="8f5ef-163">**관리 도구**를 선택 하 고 **이름 서버**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-163">Select **Management Tools**, and then select **Nameservers**.</span></span>
    
    ![Freenom 이름 서버 설정](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. <span data-ttu-id="8f5ef-165">**기본 이름 서버 사용** 이 선택 되어 있는지 확인 하 고 **이름 서버 변경을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-165">Make sure **Use default nameservers** is selected, and then select **Change Nameservers**.</span></span>
    
    ![Freenom 변경 이름 서버](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. <span data-ttu-id="8f5ef-167">**Freenom DNS 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-167">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom 관리에서 Freenom DNS를 선택 합니다.](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. <span data-ttu-id="8f5ef-169">**레코드 추가**의 **종류** 열에 있는 메뉴에서 **MX** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-169">Under **Add Record**, in the **Type** column, choose **MX** from the menu.</span></span> 
    
    ![Freenom 레코드 유형 MX 추가](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. <span data-ttu-id="8f5ef-171">새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-171">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="8f5ef-172">**이름**</span><span class="sxs-lookup"><span data-stu-id="8f5ef-172">**Name**</span></span>|<span data-ttu-id="8f5ef-173">**종류**</span><span class="sxs-lookup"><span data-stu-id="8f5ef-173">**Type**</span></span>|<span data-ttu-id="8f5ef-174">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8f5ef-174">**TTL**</span></span>|<span data-ttu-id="8f5ef-175">**Target(대상)**</span><span class="sxs-lookup"><span data-stu-id="8f5ef-175">**Target**</span></span>|<span data-ttu-id="8f5ef-176">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="8f5ef-176">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8f5ef-177">(공백으로 둠)</span><span class="sxs-lookup"><span data-stu-id="8f5ef-177">(leave blank)</span></span>  <br/> |<span data-ttu-id="8f5ef-178">MX (Mail Exchanger)(MX(메일 교환기))</span><span class="sxs-lookup"><span data-stu-id="8f5ef-178">MX (Mail Exchanger)</span></span>  <br/> |<span data-ttu-id="8f5ef-179">3600 (초)</span><span class="sxs-lookup"><span data-stu-id="8f5ef-179">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="8f5ef-180">\<\>mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="8f5ef-180">\<domain-key\>.mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="8f5ef-181">**참고:** Microsoft 계정에서 \* \<도메인 키\> \* 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-181">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="8f5ef-182">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="8f5ef-182">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="8f5ef-183">10  </span><span class="sxs-lookup"><span data-stu-id="8f5ef-183">10</span></span>  <br/> <span data-ttu-id="8f5ef-184">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-184">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
   ![Freenom MX 레코드](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. <span data-ttu-id="8f5ef-186">**변경 내용 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-186">Select **Save Changes**.</span></span>
    
    ![Freenom MX 레코드 저장 변경 내용](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. <span data-ttu-id="8f5ef-188">다른 MX 레코드가 있으면 모두 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-188">If there are any other MX records, delete them all.</span></span> <span data-ttu-id="8f5ef-189">각 레코드에 대해 **삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-189">For each record, select **Delete**.</span></span> <span data-ttu-id="8f5ef-190">**이 항목을 정말로 제거 하 시겠습니까?** 라는 메시지가 나타나면 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-190">When the message **Do you really want to remove this entry?** appears, select **OK**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="8f5ef-191">Microsoft에 필요한 CNAME 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="8f5ef-191">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="8f5ef-192"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="8f5ef-192"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="8f5ef-193">시작 하려면 [이 링크](https://my.freenom.com/)를 사용 하 여 Freenom의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-193">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="8f5ef-194">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-194">You'll be prompted to log in.</span></span>
    
    ![Freenom 로그인](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="8f5ef-196">**서비스**를 선택한 다음 **내 도메인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-196">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom 서비스 및 내 도메인 선택](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="8f5ef-198">편집 하려는 도메인에서 **도메인 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-198">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom 관리 도메인 선택](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="8f5ef-200">**Freenom DNS 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-200">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom 관리에서 Freenom DNS를 선택 합니다.](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. <span data-ttu-id="8f5ef-202">**레코드 추가**의 **종류** 열에 있는 메뉴에서 **CNAME** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-202">Under **Add Record**, in the **Type** column, choose **CNAME** from the menu.</span></span> 
    
    ![Freenom 레코드 형식 CNAME 추가](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. <span data-ttu-id="8f5ef-204">첫 번째 CNAME 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-204">Create the first CNAME record.</span></span> <span data-ttu-id="8f5ef-205">새 레코드의 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-205">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="8f5ef-206">**이름**</span><span class="sxs-lookup"><span data-stu-id="8f5ef-206">**Name**</span></span>|<span data-ttu-id="8f5ef-207">**Record type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="8f5ef-207">**Record type**</span></span>|<span data-ttu-id="8f5ef-208">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8f5ef-208">**TTL**</span></span>|<span data-ttu-id="8f5ef-209">**Target(대상)**</span><span class="sxs-lookup"><span data-stu-id="8f5ef-209">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8f5ef-210">autodiscover</span><span class="sxs-lookup"><span data-stu-id="8f5ef-210">autodiscover</span></span>  <br/> |<span data-ttu-id="8f5ef-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="8f5ef-211">CNAME</span></span>  <br/> |<span data-ttu-id="8f5ef-212">3600 (초)</span><span class="sxs-lookup"><span data-stu-id="8f5ef-212">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="8f5ef-213">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="8f5ef-213">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="8f5ef-214">sip</span><span class="sxs-lookup"><span data-stu-id="8f5ef-214">sip</span></span>  <br/> |<span data-ttu-id="8f5ef-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="8f5ef-215">CNAME</span></span>  <br/> |<span data-ttu-id="8f5ef-216">3600 (초)</span><span class="sxs-lookup"><span data-stu-id="8f5ef-216">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="8f5ef-217">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8f5ef-217">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="8f5ef-218">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="8f5ef-218">lyncdiscover</span></span>  <br/> |<span data-ttu-id="8f5ef-219">CNAME</span><span class="sxs-lookup"><span data-stu-id="8f5ef-219">CNAME</span></span>  <br/> |<span data-ttu-id="8f5ef-220">3600 (초)</span><span class="sxs-lookup"><span data-stu-id="8f5ef-220">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="8f5ef-221">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8f5ef-221">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="8f5ef-222">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="8f5ef-222">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="8f5ef-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="8f5ef-223">CNAME</span></span>  <br/> |<span data-ttu-id="8f5ef-224">3600 (초)</span><span class="sxs-lookup"><span data-stu-id="8f5ef-224">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="8f5ef-225">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="8f5ef-225">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="8f5ef-226">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="8f5ef-226">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="8f5ef-227">CNAME</span><span class="sxs-lookup"><span data-stu-id="8f5ef-227">CNAME</span></span>  <br/> |<span data-ttu-id="8f5ef-228">3600 (초)</span><span class="sxs-lookup"><span data-stu-id="8f5ef-228">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="8f5ef-229">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8f5ef-229">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Freenom CNAME 값](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. <span data-ttu-id="8f5ef-231">**변경 내용 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-231">Select **Save Changes**.</span></span>
    
    ![Freenom CNAME 저장 변경 내용](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. <span data-ttu-id="8f5ef-233">이전 단계를 반복 하 여 나머지 5 개의 CNAME 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-233">Repeat the previous steps to create the other five CNAME records.</span></span> 
    
    <span data-ttu-id="8f5ef-234">각 레코드에 대해 위 표에 있는 다음 행의 값을 해당 레코드의 상자에 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-234">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="8f5ef-235">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="8f5ef-235">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="8f5ef-236"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="8f5ef-236"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="8f5ef-237">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-237">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="8f5ef-238">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-238">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="8f5ef-239">도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-239">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="8f5ef-240">대신, 두 값 집합을 모두 포함 하는 *단일* SPF 레코드가 있도록 현재 레코드에 필수 Microsoft 값을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-240">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

1. <span data-ttu-id="8f5ef-241">시작 하려면 [이 링크](https://my.freenom.com/)를 사용 하 여 Freenom의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-241">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="8f5ef-242">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-242">You'll be prompted to log in.</span></span>
    
    ![Freenom 로그인](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="8f5ef-244">**서비스**를 선택한 다음 **내 도메인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-244">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom 서비스 및 내 도메인 선택](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="8f5ef-246">편집 하려는 도메인에서 **도메인 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-246">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom 관리 도메인 선택](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="8f5ef-248">**Freenom DNS 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-248">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom 관리에서 Freenom DNS를 선택 합니다.](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. <span data-ttu-id="8f5ef-250">**레코드 추가**의 **형식** 열에 있는 메뉴에서 **TXT** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-250">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom 레코드 형식 TXT 추가](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. <span data-ttu-id="8f5ef-252">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-252">In the boxes for the new record, type or copy and paste the following values.</span></span> 
    
    |<span data-ttu-id="8f5ef-253">**이름**</span><span class="sxs-lookup"><span data-stu-id="8f5ef-253">**Name**</span></span>|<span data-ttu-id="8f5ef-254">**Record type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="8f5ef-254">**Record type**</span></span>|<span data-ttu-id="8f5ef-255">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8f5ef-255">**TTL**</span></span>|<span data-ttu-id="8f5ef-256">**Target(대상)**</span><span class="sxs-lookup"><span data-stu-id="8f5ef-256">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8f5ef-257">(공백으로 둠)</span><span class="sxs-lookup"><span data-stu-id="8f5ef-257">(leave blank)</span></span>  <br/> |<span data-ttu-id="8f5ef-258">TXT</span><span class="sxs-lookup"><span data-stu-id="8f5ef-258">TXT</span></span>  <br/> |<span data-ttu-id="8f5ef-259">3600 (초)</span><span class="sxs-lookup"><span data-stu-id="8f5ef-259">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="8f5ef-260">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="8f5ef-260">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="8f5ef-261">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-261">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![SPF의 freenom TXT 값](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. <span data-ttu-id="8f5ef-263">**변경 내용 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f5ef-263">Select **Save Changes**.</span></span>
    
    ![SPF 저장 변경에 대 한 freenom TXT 레코드](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

