---
title: Microsoft에 대해 eNomCentral에서 DNS 레코드 만들기
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online에 대 한 DNS 레코드를 설정 하 고 Microsoft의 eNomCentral에 있는 기타 서비스를 설치 하는 방법을 알아봅니다.
ms.openlocfilehash: 33231896b69c0883bc9af3153fa57533096a1a0f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629578"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a><span data-ttu-id="b23f7-103">Microsoft에 대해 eNomCentral에서 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="b23f7-103">Create DNS records at eNomCentral for Microsoft</span></span>

 <span data-ttu-id="b23f7-104">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="b23f7-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b23f7-105">DNS 호스팅 공급자로 eNomCentral을 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-105">If eNomCentral is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="b23f7-106">ENomCentral에서 이러한 레코드를 추가 하 고 나면 도메인이 Microsoft 서비스에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-106">After you add these records at eNomCentral, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="b23f7-107">Microsoft의 웹 사이트에 대 한 호스트 및 DNS에 대 한 자세한 내용은 [microsoft에서 공개 웹 사이트 사용](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b23f7-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="b23f7-p101">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b23f7-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b23f7-111">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="b23f7-111">Add a TXT record for verification</span></span>
<span data-ttu-id="b23f7-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="b23f7-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="b23f7-113">Microsoft에서 도메인을 사용 하기 전에 사용자가 소유 하 고 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="b23f7-114">도메인 등록 기관에서 계정에 로그인 하 고 DNS 레코드를 만들 수 있는 기능은 Microsoft에 도메인을 소유 하 고 있음을 증명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b23f7-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="b23f7-117">아래 단계를 따르거나 [비디오를 시청하세요(0:46에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="b23f7-117">Follow the steps below or [watch the video (start at 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="b23f7-p104">시작하려면 [이 링크](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)를 사용하여 eNom Central의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-p104">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-구성-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="b23f7-121">**내 도메인**아래에서 편집 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-121">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-구성-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="b23f7-123">**Manage Domain(도메인 관리)** 드롭다운 목록에서 **Host Records(호스트 레코드)** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-123">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Verify-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)
  
4. <span data-ttu-id="b23f7-125">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-125">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="b23f7-126">(Choose the **Record Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="b23f7-126">(Choose the **Record Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="b23f7-127">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="b23f7-127">**Host Name**</span></span> <br/> |<span data-ttu-id="b23f7-128">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="b23f7-128">**Record Type**</span></span> <br/> |<span data-ttu-id="b23f7-129">**Address(주소)**</span><span class="sxs-lookup"><span data-stu-id="b23f7-129">**Address**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="b23f7-130">TXT</span><span class="sxs-lookup"><span data-stu-id="b23f7-130">TXT</span></span>  <br/> |<span data-ttu-id="b23f7-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b23f7-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="b23f7-132">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-132">**Note:** This is an example.</span></span> <span data-ttu-id="b23f7-133">표에서 특정 **대상 또는 지점** 값을 사용 하 여 여기서 주소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="b23f7-134">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="b23f7-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![eNom-BP-Verify-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)
  
5. <span data-ttu-id="b23f7-136">**저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-136">Select **save**.</span></span>
    
    ![eNom-BP-Verify-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)
  
6. <span data-ttu-id="b23f7-138">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b23f7-139">도메인 등록 기관 사이트에서 레코드를 추가 했으므로 이제 Microsoft 365으로 돌아가 Microsoft 365에 요청 하 여 레코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="b23f7-140">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b23f7-141">Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-141">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="b23f7-142">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="b23f7-143">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-143">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="b23f7-144">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-144">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="b23f7-p106">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b23f7-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="b23f7-148">도메인에 대 한 전자 메일이 Microsoft에 제공 되도록 MX 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="b23f7-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="b23f7-149"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="b23f7-150">아래 단계를 따르거나 [비디오를 시청하세요(3:40에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="b23f7-150">Follow the steps below or [watch the video (start at 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="b23f7-p107">시작하려면 [이 링크](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)를 사용하여 eNom Central의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-p107">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-구성-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="b23f7-154">**내 도메인**아래에서 편집 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-154">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-구성-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="b23f7-156">**Manage Domain(도메인 관리)** 드롭다운 목록에서 **Email Settings(전자 메일 설정)** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-156">On the **Manage Domain** drop-down list, choose **Email Settings**.</span></span>
    
    ![eNom-BP-구성-1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)
  
4. <span data-ttu-id="b23f7-158">**Service Selection**(서비스 선택) 드롭다운 목록에서 **User (MX)**(사용자(MX))를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-158">On the **Service Selection** drop-down list, choose **User (MX)**.</span></span>
    
    ![eNom-BP-구성-1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)
  
5. <span data-ttu-id="b23f7-160">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b23f7-160">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="b23f7-161">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="b23f7-161">**Host Name**</span></span>|<span data-ttu-id="b23f7-162">**주소**</span><span class="sxs-lookup"><span data-stu-id="b23f7-162">**Address**</span></span>|<span data-ttu-id="b23f7-163">**기본 설정**</span><span class="sxs-lookup"><span data-stu-id="b23f7-163">**Pref**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> | <span data-ttu-id="b23f7-164">*\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="b23f7-164">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="b23f7-165">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b23f7-165">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="b23f7-166">**참고:** Microsoft 계정에서 \* \<도메인 키\> \* 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-166">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="b23f7-167">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="b23f7-167">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="b23f7-168">10 </span><span class="sxs-lookup"><span data-stu-id="b23f7-168">10</span></span>  <br/> <span data-ttu-id="b23f7-169">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b23f7-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
       
   ![eNom-BP-구성-2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)
  
6. <span data-ttu-id="b23f7-171">**저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-171">Select **save**.</span></span>
    
    ![eNom-BP-구성-2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)
  
7. <span data-ttu-id="b23f7-173">기본의 다른 MX 레코드가 있으면 해당 레코드의 확인란을 선택하여 레코드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-173">If there are any other existing MX records, select the check boxes for those records to select them.</span></span>
    
    ![eNom-BP-구성-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)
  
8. <span data-ttu-id="b23f7-175">확인을 클릭 하 여 **삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-175">Select **delete checked**.</span></span>
    
    ![eNom-BP-구성-2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="b23f7-177">Microsoft에 필요한 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="b23f7-177">Add the CNAME records that are required for Microsoft</span></span> 
<span data-ttu-id="b23f7-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="b23f7-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="b23f7-179">아래 단계를 따르거나 [비디오를 시청하세요(4:24에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="b23f7-179">Follow the steps below or [watch the video (start at 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="b23f7-p109">시작하려면 [이 링크](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)를 사용하여 eNom Central의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-p109">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-구성-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="b23f7-183">**내 도메인**아래에서 편집 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-183">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-구성-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="b23f7-185">**Manage Domain(도메인 관리)** 드롭다운 목록에서 **Host Records(호스트 레코드)** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-185">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-구성-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="b23f7-187">**새 행**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-187">Select **new row**.</span></span>
    
    ![eNom-BP-구성-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)
  
5. <span data-ttu-id="b23f7-189">6개의 새 레코드 상자에서 다음 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-189">In the boxes for the six new records, type or copy and paste the following values.</span></span>
    
        (Choose the **Record Type** value from the drop-down list.) 
        
    |<span data-ttu-id="b23f7-190">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="b23f7-190">**Host Name**</span></span>|<span data-ttu-id="b23f7-191">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="b23f7-191">**Record Type**</span></span>|<span data-ttu-id="b23f7-192">**주소**</span><span class="sxs-lookup"><span data-stu-id="b23f7-192">**Address**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="b23f7-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="b23f7-193">autodiscover</span></span>  <br/> |<span data-ttu-id="b23f7-194">CNAME (Alias)(CNAME(별칭))</span><span class="sxs-lookup"><span data-stu-id="b23f7-194">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="b23f7-195">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b23f7-195">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="b23f7-196">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b23f7-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="b23f7-197">sip</span><span class="sxs-lookup"><span data-stu-id="b23f7-197">sip</span></span>  <br/> |<span data-ttu-id="b23f7-198">CNAME (Alias)(CNAME(별칭))</span><span class="sxs-lookup"><span data-stu-id="b23f7-198">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="b23f7-199">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b23f7-199">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="b23f7-200">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b23f7-200">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="b23f7-201">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="b23f7-201">lyncdiscover</span></span>  <br/> |<span data-ttu-id="b23f7-202">CNAME (Alias)(CNAME(별칭))</span><span class="sxs-lookup"><span data-stu-id="b23f7-202">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="b23f7-203">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b23f7-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="b23f7-204">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b23f7-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="b23f7-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="b23f7-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="b23f7-206">CNAME (Alias)(CNAME(별칭))</span><span class="sxs-lookup"><span data-stu-id="b23f7-206">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="b23f7-207">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="b23f7-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="b23f7-208">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b23f7-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="b23f7-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="b23f7-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="b23f7-210">CNAME (Alias)(CNAME(별칭))</span><span class="sxs-lookup"><span data-stu-id="b23f7-210">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="b23f7-211">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b23f7-211">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="b23f7-212">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b23f7-212">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-구성-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)
  
6. <span data-ttu-id="b23f7-214">**저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-214">Select **save**.</span></span>
    
    ![eNom-BP-구성-3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="b23f7-216">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="b23f7-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="b23f7-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="b23f7-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b23f7-218">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="b23f7-219">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="b23f7-220">도메인에 대 한 SPF 레코드가 이미 있는 경우 Microsoft에 대해 새로 만들지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="b23f7-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="b23f7-221">대신, 두 값 집합을 모두 포함 하는 *단일* SPF 레코드가 있도록 현재 레코드에 필수 Microsoft 값을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="b23f7-222">아래 단계를 따르거나 [비디오를 시청하세요(5:12에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="b23f7-222">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="b23f7-p111">시작하려면 [이 링크](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)를 사용하여 eNom Central의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-p111">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-구성-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="b23f7-226">**내 도메인**아래에서 편집 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-226">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-구성-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="b23f7-228">**Manage Domain(도메인 관리)** 드롭다운 목록에서 **Host Records(호스트 레코드)** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-228">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-구성-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="b23f7-230">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-230">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="b23f7-231">(Choose the **Record Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="b23f7-231">(Choose the **Record Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="b23f7-232">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="b23f7-232">**Host Name**</span></span>|<span data-ttu-id="b23f7-233">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="b23f7-233">**Record Type**</span></span>|<span data-ttu-id="b23f7-234">**Address(주소)**</span><span class="sxs-lookup"><span data-stu-id="b23f7-234">**Address**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="b23f7-235">TXT</span><span class="sxs-lookup"><span data-stu-id="b23f7-235">TXT</span></span>  <br/> |<span data-ttu-id="b23f7-236">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="b23f7-236">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="b23f7-237">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-237">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![eNom-BP-구성-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)
  
5. <span data-ttu-id="b23f7-239">**저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-239">Select **save**.</span></span>
    
    ![eNom-BP-구성-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="b23f7-241">Microsoft에 필요한 두 개의 SRV 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="b23f7-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="b23f7-242"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="b23f7-243">아래 단계를 따르거나 [비디오를 시청하세요(5:50에 시작)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="b23f7-243">Follow the steps below or [watch the video (start at 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="b23f7-p112">시작하려면 [이 링크](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)를 사용하여 eNom Central의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-p112">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-구성-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="b23f7-247">**내 도메인**아래에서 편집 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-247">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-구성-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="b23f7-249">**Manage Domain(도메인 관리)** 드롭다운 목록에서 **Host Records(호스트 레코드)** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-249">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-구성-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="b23f7-251">**새 행**오른쪽에서 **SRV 또는 SPF 레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-251">To the right of **new row**, select **add SRV or SPF record**.</span></span>
    
    ![eNom-BP-구성-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)
  
5. <span data-ttu-id="b23f7-253">두 개의 새 레코드 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="b23f7-253">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="b23f7-254">**서비스**</span><span class="sxs-lookup"><span data-stu-id="b23f7-254">**Service**</span></span>|<span data-ttu-id="b23f7-255">**프로토콜**</span><span class="sxs-lookup"><span data-stu-id="b23f7-255">**Protocol**</span></span>|<span data-ttu-id="b23f7-256">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="b23f7-256">**Priority**</span></span>|<span data-ttu-id="b23f7-257">**Weight(가중치)**</span><span class="sxs-lookup"><span data-stu-id="b23f7-257">**Weight**</span></span>|<span data-ttu-id="b23f7-258">**Port(포트)**</span><span class="sxs-lookup"><span data-stu-id="b23f7-258">**Port**</span></span>|<span data-ttu-id="b23f7-259">**대상          (호스트 이름)**</span><span class="sxs-lookup"><span data-stu-id="b23f7-259">**Target          (Hostname)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b23f7-260">_sip</span><span class="sxs-lookup"><span data-stu-id="b23f7-260">_sip</span></span>  <br/> |<span data-ttu-id="b23f7-261">_tls</span><span class="sxs-lookup"><span data-stu-id="b23f7-261">_tls</span></span>  <br/> |<span data-ttu-id="b23f7-262">100</span><span class="sxs-lookup"><span data-stu-id="b23f7-262">100</span></span>  <br/> |<span data-ttu-id="b23f7-263">1 </span><span class="sxs-lookup"><span data-stu-id="b23f7-263">1</span></span>  <br/> |<span data-ttu-id="b23f7-264">443</span><span class="sxs-lookup"><span data-stu-id="b23f7-264">443</span></span>  <br/> |<span data-ttu-id="b23f7-265">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b23f7-265">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="b23f7-266">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b23f7-266">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="b23f7-267">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="b23f7-267">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="b23f7-268">_tcp</span><span class="sxs-lookup"><span data-stu-id="b23f7-268">_tcp</span></span>  <br/> |<span data-ttu-id="b23f7-269">100</span><span class="sxs-lookup"><span data-stu-id="b23f7-269">100</span></span>  <br/> |<span data-ttu-id="b23f7-270">1 </span><span class="sxs-lookup"><span data-stu-id="b23f7-270">1</span></span>  <br/> |<span data-ttu-id="b23f7-271">5061</span><span class="sxs-lookup"><span data-stu-id="b23f7-271">5061</span></span>  <br/> |<span data-ttu-id="b23f7-272">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b23f7-272">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="b23f7-273">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b23f7-273">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-구성-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)
  
6. <span data-ttu-id="b23f7-275">**저장** 을 선택</span><span class="sxs-lookup"><span data-stu-id="b23f7-275">Select **save**</span></span>
    
    ![eNom-BP-구성-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)
  
> [!NOTE]
>  <span data-ttu-id="b23f7-p113">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b23f7-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

