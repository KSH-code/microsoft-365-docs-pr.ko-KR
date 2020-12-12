---
title: Netregistry에서 Microsoft용 DNS 레코드 만들기
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
- BEA160
ms.assetid: 48e09394-2287-4b3c-9853-21eadf61277e
description: Microsoft용 Netregistry에서 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대한 DNS 레코드를 설정하는 방법을 학습합니다.
ms.openlocfilehash: 857645c685cce946b39a7c3dcadb0a45b43686cf
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657806"
---
# <a name="create-dns-records-at-netregistry-for-microsoft"></a><span data-ttu-id="52420-103">Netregistry에서 Microsoft용 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="52420-103">Create DNS records at Netregistry for Microsoft</span></span>

<span data-ttu-id="52420-104">원하는 정보를 찾지 못한 경우 [도메인 FAQ를 확인](../setup/domains-faq.yml)하세요.</span><span class="sxs-lookup"><span data-stu-id="52420-104">[Check the Domains FAQ](../setup/domains-faq.yml) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="52420-105">DNS 호스팅 공급자로 Netregistry를 사용하고 있는 경우 이 문서의 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online에 대한 DNS 레코드를 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="52420-105">If Netregistry is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="52420-106">다음은 추가할 기본 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="52420-106">These are the main records to add.</span></span>
  
- [<span data-ttu-id="52420-107">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="52420-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="52420-108">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="52420-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)

- [<span data-ttu-id="52420-109">Microsoft에 필요한 CNAME 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="52420-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="52420-110">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="52420-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="52420-111">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="52420-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="52420-112">Netregistry에서 이러한 레코드를 추가하고 나면 도메인이 Microsoft 서비스에서 작동하게 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="52420-112">After you add these records at Netregistry, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="52420-p101">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52420-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="52420-116">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="52420-116">Add a TXT record for verification</span></span>
<span data-ttu-id="52420-117"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="52420-117"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="52420-p102">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52420-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="52420-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52420-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="52420-122">시작하려면 이 링크를 사용하여 Netregistry의 도메인 [페이지로 이동합니다.](https://theconsole.netregistry.com.au/)</span><span class="sxs-lookup"><span data-stu-id="52420-122">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="52420-123">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="52420-123">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. <span data-ttu-id="52420-125">관리하려는 도메인 옆에서 관리 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="52420-125">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. <span data-ttu-id="52420-127">영역 **관리자를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="52420-127">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. <span data-ttu-id="52420-129">영역 **레코드 추가 목록에서** **TXT** 레코드를 선택한 다음 새 레코드 **만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="52420-129">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > <span data-ttu-id="52420-131">TXT 상자의 항목 앞과 뒤에서 인용 부호를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52420-131">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    <span data-ttu-id="52420-132">새 **TXT 레코드** 폼에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="52420-132">In the **New TXT Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="52420-133">**이름**</span><span class="sxs-lookup"><span data-stu-id="52420-133">**Name**</span></span>|<span data-ttu-id="52420-134">**TTL(SEC)**</span><span class="sxs-lookup"><span data-stu-id="52420-134">**TTL (SEC)**</span></span>|<span data-ttu-id="52420-135">**TXT(주소 또는 값 포인트)**</span><span class="sxs-lookup"><span data-stu-id="52420-135">**TXT (Points to address or value)**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="52420-136">(공백으로 둠)</span><span class="sxs-lookup"><span data-stu-id="52420-136">(leave blank)</span></span>  <br/> |<span data-ttu-id="52420-137">3600(초)</span><span class="sxs-lookup"><span data-stu-id="52420-137">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="52420-138">"MS=msXXXXXXXXX"</span><span class="sxs-lookup"><span data-stu-id="52420-138">"MS=msXXXXXXXX"</span></span>  <br/> <span data-ttu-id="52420-139">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="52420-139">**Note:** This is an example.</span></span> <span data-ttu-id="52420-140">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="52420-140">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="52420-141">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="52420-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. <span data-ttu-id="52420-143">레코드 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="52420-143">Select **Add record**.</span></span>
    
<span data-ttu-id="52420-144">이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="52420-144">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="52420-145">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="52420-145">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="52420-146">I관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인</a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="52420-146">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="52420-147">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52420-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="52420-148">**설정** 페이지에서 **설정 시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52420-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="52420-149">**도메인 확인** 페이지에서 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52420-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="52420-p106">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52420-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="52420-153">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="52420-153">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="52420-154"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="52420-154"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="52420-155">시작하려면 이 링크를 사용하여 Netregistry의 도메인 [페이지로 이동합니다.](https://theconsole.netregistry.com.au/)</span><span class="sxs-lookup"><span data-stu-id="52420-155">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="52420-156">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="52420-156">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. <span data-ttu-id="52420-158">관리하려는 도메인 옆에서 관리 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="52420-158">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. <span data-ttu-id="52420-160">영역 **관리자를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="52420-160">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. <span data-ttu-id="52420-162">현재 **영역 레코드에서** 목록의 각 MX  레코드 옆에 있는 제거를 선택하여 기본 MX 레코드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="52420-162">Under **Current zone records**, remove the default MX records by selecting **Remove** next to each MX record in the list.</span></span> 
    
    ![Netregistry_MX_remove](../../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. <span data-ttu-id="52420-164">영역 **레코드 추가 아래** 목록에서 **MX** 레코드를 선택한 다음 새 레코드 **만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="52420-164">Under **Add a zone record**, choose **MX Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_MX_select](../../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. <span data-ttu-id="52420-166">새 **MX 레코드** 폼에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="52420-166">In the **New MX Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="52420-167">**이름**</span><span class="sxs-lookup"><span data-stu-id="52420-167">**Name**</span></span>|<span data-ttu-id="52420-168">**TTL(SEC)**</span><span class="sxs-lookup"><span data-stu-id="52420-168">**TTL (SEC)**</span></span>|<span data-ttu-id="52420-169">**Exchange(주소 또는 값 포인트)**</span><span class="sxs-lookup"><span data-stu-id="52420-169">**Exchange (Points to address or value)**</span></span>|<span data-ttu-id="52420-170">**호스트가 정식으로 자격을 갖춘가요?**</span><span class="sxs-lookup"><span data-stu-id="52420-170">**Is host fully qualified?**</span></span>|<span data-ttu-id="52420-171">**기본 설정(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="52420-171">**Preference (Priority)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="52420-172">(공백으로 둠)</span><span class="sxs-lookup"><span data-stu-id="52420-172">(leave blank)</span></span>  <br/> |<span data-ttu-id="52420-173">3600(초)</span><span class="sxs-lookup"><span data-stu-id="52420-173">3600 (seconds)</span></span>  <br/> | <span data-ttu-id="52420-174">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="52420-174">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="52420-175">**참고:** Microsoft  *\<domain-key\>*  계정에서 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="52420-175">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="52420-176">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="52420-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      |<span data-ttu-id="52420-177">(확인란 선택)</span><span class="sxs-lookup"><span data-stu-id="52420-177">(select the checkbox)</span></span>  <br/> |<span data-ttu-id="52420-178">10 </span><span class="sxs-lookup"><span data-stu-id="52420-178">10</span></span>  <br/> <span data-ttu-id="52420-179">For more information about priority, see What is MX priority?</span><span class="sxs-lookup"><span data-stu-id="52420-179">For more information about priority, see What is MX priority?</span></span>  <br/> |
       
    ![Netregistry_MX_values](../../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. <span data-ttu-id="52420-181">레코드 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="52420-181">Select **Add Record**.</span></span>
    
    ![Netregistry_MX_values_AddRecord](../../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="52420-183">Microsoft에 필요한 CNAME 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="52420-183">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="52420-184"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="52420-184"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="52420-185">시작하려면 이 링크를 사용하여 Netregistry의 도메인 [페이지로 이동합니다.](https://theconsole.netregistry.com.au/)</span><span class="sxs-lookup"><span data-stu-id="52420-185">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="52420-186">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="52420-186">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. <span data-ttu-id="52420-188">관리하려는 도메인 옆에서 관리 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="52420-188">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. <span data-ttu-id="52420-190">영역 **관리자를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="52420-190">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. <span data-ttu-id="52420-192">영역 **레코드 추가 목록에서** **CNAME** 레코드를 선택한 다음 새 레코드 **만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="52420-192">Under  **Add a zone record**, choose **CNAME Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_CNAME_CreateNewRecord](../../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. <span data-ttu-id="52420-194">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="52420-194">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="52420-195">**이름**</span><span class="sxs-lookup"><span data-stu-id="52420-195">**Name**</span></span>|<span data-ttu-id="52420-196">**Type(종류)**</span><span class="sxs-lookup"><span data-stu-id="52420-196">**Type**</span></span>|<span data-ttu-id="52420-197">**TTL**</span><span class="sxs-lookup"><span data-stu-id="52420-197">**TTL**</span></span>|<span data-ttu-id="52420-198">**HOST(Points to or address value)**</span><span class="sxs-lookup"><span data-stu-id="52420-198">**HOST (Points to or address value)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="52420-199">autodiscover</span><span class="sxs-lookup"><span data-stu-id="52420-199">autodiscover</span></span>  <br/> |<span data-ttu-id="52420-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="52420-200">CNAME</span></span>  <br/> |<span data-ttu-id="52420-201">3600(초)</span><span class="sxs-lookup"><span data-stu-id="52420-201">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="52420-202">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="52420-202">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="52420-203">sip</span><span class="sxs-lookup"><span data-stu-id="52420-203">sip</span></span>  <br/> |<span data-ttu-id="52420-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="52420-204">CNAME</span></span>  <br/> |<span data-ttu-id="52420-205">3600(초)</span><span class="sxs-lookup"><span data-stu-id="52420-205">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="52420-206">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="52420-206">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="52420-207">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="52420-207">lyncdiscover</span></span>  <br/> |<span data-ttu-id="52420-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="52420-208">CNAME</span></span>  <br/> |<span data-ttu-id="52420-209">3600(초)</span><span class="sxs-lookup"><span data-stu-id="52420-209">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="52420-210">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="52420-210">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="52420-211">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="52420-211">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="52420-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="52420-212">CNAME</span></span>  <br/> |<span data-ttu-id="52420-213">3600(초)</span><span class="sxs-lookup"><span data-stu-id="52420-213">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="52420-214">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="52420-214">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="52420-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="52420-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="52420-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="52420-216">CNAME</span></span>  <br/> |<span data-ttu-id="52420-217">3600(초)</span><span class="sxs-lookup"><span data-stu-id="52420-217">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="52420-218">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="52420-218">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![Netregistry_CNAME_values](../../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. <span data-ttu-id="52420-220">레코드 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="52420-220">Select **Add record**.</span></span>
    
    ![Netregistry_CNAME_values_AddRecord](../../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. <span data-ttu-id="52420-222">이전 단계를 반복하여 나머지 5개의 CNAME 레코드를 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="52420-222">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="52420-223">각 레코드에 대해 위 표의 다음 행 값을 해당 레코드의 상자에 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="52420-223">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="52420-224">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="52420-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="52420-225"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="52420-225"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="52420-226">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="52420-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="52420-227">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52420-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="52420-228">도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="52420-228">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="52420-229">대신 두 값 집합을 모두 포함하는  *단일*  SPF 레코드가 있도록 현재 레코드에 필요한 Microsoft 값을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="52420-229">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="52420-230">시작하려면 이 링크를 사용하여 Netregistry의 도메인 [페이지로 이동합니다.](https://theconsole.netregistry.com.au/)</span><span class="sxs-lookup"><span data-stu-id="52420-230">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="52420-231">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="52420-231">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. <span data-ttu-id="52420-233">관리하려는 도메인 옆에서 관리 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="52420-233">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. <span data-ttu-id="52420-235">영역 **관리자를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="52420-235">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. <span data-ttu-id="52420-237">영역 **레코드 추가 목록에서** **TXT** 레코드를 선택한 다음 새 레코드 **만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="52420-237">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. <span data-ttu-id="52420-239">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="52420-239">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="52420-240">TXT 상자의 항목 앞과 뒤에서 인용 부호를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52420-240">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    |<span data-ttu-id="52420-241">**이름**</span><span class="sxs-lookup"><span data-stu-id="52420-241">**Name**</span></span>|<span data-ttu-id="52420-242">**Type(종류)**</span><span class="sxs-lookup"><span data-stu-id="52420-242">**Type**</span></span>|<span data-ttu-id="52420-243">**TTL**</span><span class="sxs-lookup"><span data-stu-id="52420-243">**TTL**</span></span>|<span data-ttu-id="52420-244">**TXT 데이터(대상)**</span><span class="sxs-lookup"><span data-stu-id="52420-244">**TXT Data (Target)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="52420-245">(공백으로 둠)</span><span class="sxs-lookup"><span data-stu-id="52420-245">(leave blank)</span></span>  <br/> |<span data-ttu-id="52420-246">TXT</span><span class="sxs-lookup"><span data-stu-id="52420-246">TXT</span></span>  <br/> |<span data-ttu-id="52420-247">3600(초)</span><span class="sxs-lookup"><span data-stu-id="52420-247">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="52420-248">"v=spf1 include:spf.protection.outlook.com -all"</span><span class="sxs-lookup"><span data-stu-id="52420-248">"v=spf1 include:spf.protection.outlook.com -all"</span></span>  <br/> <span data-ttu-id="52420-249">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="52420-249">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Netregistry_SPF-TXTvalues](../../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. <span data-ttu-id="52420-251">레코드 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="52420-251">Select **Add Record**.</span></span>
    
    ![Netregistry_SPF-TXTvalues_AddRecord](../../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="52420-253">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="52420-253">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="52420-254"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="52420-254"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="52420-255">시작하려면 이 링크를 사용하여 Netregistry의 도메인 [페이지로 이동합니다.](https://theconsole.netregistry.com.au/)</span><span class="sxs-lookup"><span data-stu-id="52420-255">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="52420-256">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="52420-256">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. <span data-ttu-id="52420-258">관리하려는 도메인 옆에서 관리 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="52420-258">Next to the domain you want to manage, select  **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. <span data-ttu-id="52420-260">영역 **관리자를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="52420-260">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. <span data-ttu-id="52420-262">영역 **레코드 추가 아래** 목록에서 **SRV** 레코드를 선택한 다음 새 레코드 **만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="52420-262">Under  **Add a zone record**, choose **SRV Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_SRV_select](../../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. <span data-ttu-id="52420-264">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="52420-264">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="52420-265">Name 필드는 서비스(예: _sip) 및 프로토콜(예: _tls)의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="52420-265">The Name field is a combination of the service (for example, _sip) and protocol (for example, _tls).</span></span> 
  
    |<span data-ttu-id="52420-266">**유형**</span><span class="sxs-lookup"><span data-stu-id="52420-266">**Type**</span></span>|<span data-ttu-id="52420-267">**이름**</span><span class="sxs-lookup"><span data-stu-id="52420-267">**Name**</span></span>|<span data-ttu-id="52420-268">**TTL(SEC)**</span><span class="sxs-lookup"><span data-stu-id="52420-268">**TTL (SEC)**</span></span>|<span data-ttu-id="52420-269">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="52420-269">**Priority**</span></span>|<span data-ttu-id="52420-270">**Weight(가중치)**</span><span class="sxs-lookup"><span data-stu-id="52420-270">**Weight**</span></span>|<span data-ttu-id="52420-271">**Port(포트)**</span><span class="sxs-lookup"><span data-stu-id="52420-271">**Port**</span></span>|<span data-ttu-id="52420-272">**대상**</span><span class="sxs-lookup"><span data-stu-id="52420-272">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="52420-273">SRV(서비스)</span><span class="sxs-lookup"><span data-stu-id="52420-273">SRV (service)</span></span>  <br/> |<span data-ttu-id="52420-274">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="52420-274">_sip._tls</span></span>  <br/> |<span data-ttu-id="52420-275">3600(초)</span><span class="sxs-lookup"><span data-stu-id="52420-275">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="52420-276">100</span><span class="sxs-lookup"><span data-stu-id="52420-276">100</span></span>  <br/> |<span data-ttu-id="52420-277">1 </span><span class="sxs-lookup"><span data-stu-id="52420-277">1</span></span>  <br/> |<span data-ttu-id="52420-278">443</span><span class="sxs-lookup"><span data-stu-id="52420-278">443</span></span>  <br/> |<span data-ttu-id="52420-279">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="52420-279">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="52420-280">SRV(서비스)</span><span class="sxs-lookup"><span data-stu-id="52420-280">SRV (service)</span></span>  <br/> |<span data-ttu-id="52420-281">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="52420-281">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="52420-282">3600(초)</span><span class="sxs-lookup"><span data-stu-id="52420-282">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="52420-283">100</span><span class="sxs-lookup"><span data-stu-id="52420-283">100</span></span>  <br/> |<span data-ttu-id="52420-284">1 </span><span class="sxs-lookup"><span data-stu-id="52420-284">1</span></span>  <br/> |<span data-ttu-id="52420-285">5061</span><span class="sxs-lookup"><span data-stu-id="52420-285">5061</span></span>  <br/> |<span data-ttu-id="52420-286">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="52420-286">sipfed.online.lync.com</span></span>  <br/> |
       
    ![Netregistry_SRV_values](../../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. <span data-ttu-id="52420-288">레코드 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="52420-288">Select **Add Record**.</span></span>
    
    ![Netregistry_SRV_values_AddRecord](../../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. <span data-ttu-id="52420-290">이전 단계를 반복하여 다른 SRV 레코드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52420-290">Repeat the previous steps to create the other SRV record.</span></span>
    
    <span data-ttu-id="52420-291">위 표에 있는 두 번째 행의 값을 두 번째 레코드의 상자에 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="52420-291">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="52420-p113">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52420-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

