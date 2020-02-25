---
title: Office 365에 대 한 Netregistry에서 DNS 레코드 만들기
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
- BEA160
ms.assetid: 48e09394-2287-4b3c-9853-21eadf61277e
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스 (예를 들어 Office 365 용 Netregistry)에 대 한 DNS 레코드를 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: de4e16fa20f950edef8d30b4c6d02214e3753b9c
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42254675"
---
# <a name="create-dns-records-at-netregistry-for-office-365"></a><span data-ttu-id="15d9d-103">Office 365에 대 한 Netregistry에서 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="15d9d-103">Create DNS records at Netregistry for Office 365</span></span>

<span data-ttu-id="15d9d-104">원하는 정보를 찾지 못한 경우 [도메인 FAQ를 확인](../setup/domains-faq.md)하세요.</span><span class="sxs-lookup"><span data-stu-id="15d9d-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="15d9d-105">Netregistry가 DNS 호스팅 공급자 이면이 문서에 나와 있는 단계에 따라 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 등에 대 한 DNS 레코드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-105">If Netregistry is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="15d9d-106">다음은 추가할 기본 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-106">These are the main records to add.</span></span>
  
- [<span data-ttu-id="15d9d-107">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="15d9d-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="15d9d-108">사용자 도메인의 전자 메일이 Office 365로 전송되도록 MX 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="15d9d-108">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)

- [<span data-ttu-id="15d9d-109">Office 365에 필요한 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="15d9d-109">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="15d9d-110">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="15d9d-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="15d9d-111">Office 365에 필요한 2개의 SRV 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="15d9d-111">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="15d9d-112">Netregistry에서 이러한 레코드를 추가 하 고 나면 도메인이 Office 365 서비스에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-112">After you add these records at Netregistry, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="15d9d-113">Office 365에서 웹 사이트의 웹 호스팅 및 DNS에 대한 자세한 내용은 [Office 365에서 공개 웹 사이트 사용](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="15d9d-113">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="15d9d-p101">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="15d9d-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="15d9d-117">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="15d9d-117">Add a TXT record for verification</span></span>
<span data-ttu-id="15d9d-118"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="15d9d-118"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="15d9d-p102">Office 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Office 365에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="15d9d-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="15d9d-123">시작 하려면 [이 링크](https://theconsole.netregistry.com.au/)를 사용 하 여 netregistry의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-123">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="15d9d-124">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="15d9d-124">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. <span data-ttu-id="15d9d-126">관리할 도메인 옆에 있는 **관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-126">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. <span data-ttu-id="15d9d-128">**영역 관리자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-128">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. <span data-ttu-id="15d9d-130">**영역 레코드 추가**의 목록에서 **TXT 레코드** 를 선택 하 고 **새 레코드 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-130">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > <span data-ttu-id="15d9d-132">TXT 상자의 항목 앞뒤에는 따옴표를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-132">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    <span data-ttu-id="15d9d-133">**새 TXT 레코드** 폼에서 다음 표의 값을 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-133">In the **New TXT Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="15d9d-134">**이름**</span><span class="sxs-lookup"><span data-stu-id="15d9d-134">**Name**</span></span>|<span data-ttu-id="15d9d-135">**TTL (초)**</span><span class="sxs-lookup"><span data-stu-id="15d9d-135">**TTL (SEC)**</span></span>|<span data-ttu-id="15d9d-136">**TXT (주소 또는 값에 가리키기)**</span><span class="sxs-lookup"><span data-stu-id="15d9d-136">**TXT (Points to address or value)**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="15d9d-137">(공백으로 둠)</span><span class="sxs-lookup"><span data-stu-id="15d9d-137">(leave blank)</span></span>  <br/> |<span data-ttu-id="15d9d-138">3600 (초)</span><span class="sxs-lookup"><span data-stu-id="15d9d-138">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="15d9d-139">"MS = msXXXXXXXX"</span><span class="sxs-lookup"><span data-stu-id="15d9d-139">"MS=msXXXXXXXX"</span></span>  <br/> <span data-ttu-id="15d9d-140">**참고:** 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-140">**Note:** This is an example.</span></span> <span data-ttu-id="15d9d-141">여기에는 Office 365의 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-141">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="15d9d-142">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="15d9d-142">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. <span data-ttu-id="15d9d-144">**레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-144">Select **Add record**.</span></span>
    
<span data-ttu-id="15d9d-145">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="15d9d-145">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="15d9d-146">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="15d9d-146">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="15d9d-147">관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-147">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="15d9d-148">**도메인** 페이지에서 확인 하려는 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-148">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="15d9d-149">**설정** 페이지에서 **설정 시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-149">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="15d9d-150">**도메인 확인** 페이지에서 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-150">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="15d9d-p106">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="15d9d-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="15d9d-154">사용자 도메인의 전자 메일이 Office 365로 전송되도록 MX 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="15d9d-154">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="15d9d-155"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="15d9d-155"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="15d9d-156">시작 하려면 [이 링크](https://theconsole.netregistry.com.au/)를 사용 하 여 netregistry의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-156">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="15d9d-157">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="15d9d-157">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. <span data-ttu-id="15d9d-159">관리할 도메인 옆에 있는 **관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-159">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. <span data-ttu-id="15d9d-161">**영역 관리자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-161">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. <span data-ttu-id="15d9d-163">**현재 영역 레코드**에서 목록의 각 MX 레코드 옆에 있는 **제거** 를 선택 하 여 기본 MX 레코드를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-163">Under **Current zone records**, remove the default MX records by selecting **Remove** next to each MX record in the list.</span></span> 
    
    ![Netregistry_MX_remove](../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. <span data-ttu-id="15d9d-165">**영역 레코드 추가**아래의 목록에서 **MX 레코드** 를 선택한 다음 **새 레코드 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-165">Under **Add a zone record**, choose **MX Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_MX_select](../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. <span data-ttu-id="15d9d-167">**새 MX 레코드** 폼에서 다음 표의 값을 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-167">In the **New MX Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="15d9d-168">**이름**</span><span class="sxs-lookup"><span data-stu-id="15d9d-168">**Name**</span></span>|<span data-ttu-id="15d9d-169">**TTL (초)**</span><span class="sxs-lookup"><span data-stu-id="15d9d-169">**TTL (SEC)**</span></span>|<span data-ttu-id="15d9d-170">**Exchange (주소 또는 값을 가리키도록)**</span><span class="sxs-lookup"><span data-stu-id="15d9d-170">**Exchange (Points to address or value)**</span></span>|<span data-ttu-id="15d9d-171">**호스트 정규화 여부**</span><span class="sxs-lookup"><span data-stu-id="15d9d-171">**Is host fully qualified?**</span></span>|<span data-ttu-id="15d9d-172">**기본 설정 (우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="15d9d-172">**Preference (Priority)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="15d9d-173">(공백으로 둠)</span><span class="sxs-lookup"><span data-stu-id="15d9d-173">(leave blank)</span></span>  <br/> |<span data-ttu-id="15d9d-174">3600 (초)</span><span class="sxs-lookup"><span data-stu-id="15d9d-174">3600 (seconds)</span></span>  <br/> | <span data-ttu-id="15d9d-175">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="15d9d-175">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="15d9d-176">**참고:** Office 365 계정에서 \* \<도메인\> 키\* 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-176">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="15d9d-177">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="15d9d-177">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      |<span data-ttu-id="15d9d-178">(확인란 선택)</span><span class="sxs-lookup"><span data-stu-id="15d9d-178">(select the checkbox)</span></span>  <br/> |<span data-ttu-id="15d9d-179">10 </span><span class="sxs-lookup"><span data-stu-id="15d9d-179">10</span></span>  <br/> <span data-ttu-id="15d9d-180">For more information about priority, see What is MX priority?</span><span class="sxs-lookup"><span data-stu-id="15d9d-180">For more information about priority, see What is MX priority?</span></span>  <br/> |
       
    ![Netregistry_MX_values](../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. <span data-ttu-id="15d9d-182">**레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-182">Select **Add Record**.</span></span>
    
    ![Netregistry_MX_values_AddRecord](../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="15d9d-184">Office 365에 필요한 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="15d9d-184">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="15d9d-185"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="15d9d-185"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="15d9d-186">시작 하려면 [이 링크](https://theconsole.netregistry.com.au/)를 사용 하 여 netregistry의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-186">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="15d9d-187">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="15d9d-187">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. <span data-ttu-id="15d9d-189">관리할 도메인 옆에 있는 **관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-189">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. <span data-ttu-id="15d9d-191">**영역 관리자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-191">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. <span data-ttu-id="15d9d-193">**영역 레코드 추가**아래의 목록에서 **CNAME 레코드** 를 선택 하 고 **새 레코드 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-193">Under  **Add a zone record**, choose **CNAME Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_CNAME_CreateNewRecord](../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. <span data-ttu-id="15d9d-195">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="15d9d-195">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="15d9d-196">**이름**</span><span class="sxs-lookup"><span data-stu-id="15d9d-196">**Name**</span></span>|<span data-ttu-id="15d9d-197">**종류**</span><span class="sxs-lookup"><span data-stu-id="15d9d-197">**Type**</span></span>|<span data-ttu-id="15d9d-198">**TTL**</span><span class="sxs-lookup"><span data-stu-id="15d9d-198">**TTL**</span></span>|<span data-ttu-id="15d9d-199">**호스트 (포인트 또는 주소 값)**</span><span class="sxs-lookup"><span data-stu-id="15d9d-199">**HOST (Points to or address value)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="15d9d-200">autodiscover</span><span class="sxs-lookup"><span data-stu-id="15d9d-200">autodiscover</span></span>  <br/> |<span data-ttu-id="15d9d-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="15d9d-201">CNAME</span></span>  <br/> |<span data-ttu-id="15d9d-202">3600 (초)</span><span class="sxs-lookup"><span data-stu-id="15d9d-202">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="15d9d-203">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="15d9d-203">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="15d9d-204">sip</span><span class="sxs-lookup"><span data-stu-id="15d9d-204">sip</span></span>  <br/> |<span data-ttu-id="15d9d-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="15d9d-205">CNAME</span></span>  <br/> |<span data-ttu-id="15d9d-206">3600 (초)</span><span class="sxs-lookup"><span data-stu-id="15d9d-206">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="15d9d-207">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="15d9d-207">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="15d9d-208">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="15d9d-208">lyncdiscover</span></span>  <br/> |<span data-ttu-id="15d9d-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="15d9d-209">CNAME</span></span>  <br/> |<span data-ttu-id="15d9d-210">3600 (초)</span><span class="sxs-lookup"><span data-stu-id="15d9d-210">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="15d9d-211">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="15d9d-211">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="15d9d-212">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="15d9d-212">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="15d9d-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="15d9d-213">CNAME</span></span>  <br/> |<span data-ttu-id="15d9d-214">3600 (초)</span><span class="sxs-lookup"><span data-stu-id="15d9d-214">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="15d9d-215">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="15d9d-215">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="15d9d-216">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="15d9d-216">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="15d9d-217">CNAME</span><span class="sxs-lookup"><span data-stu-id="15d9d-217">CNAME</span></span>  <br/> |<span data-ttu-id="15d9d-218">3600 (초)</span><span class="sxs-lookup"><span data-stu-id="15d9d-218">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="15d9d-219">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="15d9d-219">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![Netregistry_CNAME_values](../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. <span data-ttu-id="15d9d-221">**레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-221">Select **Add record**.</span></span>
    
    ![Netregistry_CNAME_values_AddRecord](../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. <span data-ttu-id="15d9d-223">이전 단계를 반복 하 여 나머지 5 개의 CNAME 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-223">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="15d9d-224">각 레코드에 대해 위 표에 있는 다음 행의 값을 해당 레코드의 상자에 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-224">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="15d9d-225">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="15d9d-225">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="15d9d-226"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="15d9d-226"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="15d9d-227">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="15d9d-227">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="15d9d-228">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="15d9d-228">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="15d9d-229">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="15d9d-229">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="15d9d-230">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="15d9d-230">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="15d9d-231">시작 하려면 [이 링크](https://theconsole.netregistry.com.au/)를 사용 하 여 netregistry의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-231">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="15d9d-232">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="15d9d-232">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. <span data-ttu-id="15d9d-234">관리할 도메인 옆에 있는 **관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-234">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. <span data-ttu-id="15d9d-236">**영역 관리자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-236">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. <span data-ttu-id="15d9d-238">**영역 레코드 추가**의 목록에서 **TXT 레코드** 를 선택 하 고 **새 레코드 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-238">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. <span data-ttu-id="15d9d-240">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="15d9d-240">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="15d9d-241">TXT 상자의 항목 앞뒤에는 따옴표를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-241">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    |<span data-ttu-id="15d9d-242">**이름**</span><span class="sxs-lookup"><span data-stu-id="15d9d-242">**Name**</span></span>|<span data-ttu-id="15d9d-243">**종류**</span><span class="sxs-lookup"><span data-stu-id="15d9d-243">**Type**</span></span>|<span data-ttu-id="15d9d-244">**TTL**</span><span class="sxs-lookup"><span data-stu-id="15d9d-244">**TTL**</span></span>|<span data-ttu-id="15d9d-245">**TXT 데이터 (대상)**</span><span class="sxs-lookup"><span data-stu-id="15d9d-245">**TXT Data (Target)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="15d9d-246">(공백으로 둠)</span><span class="sxs-lookup"><span data-stu-id="15d9d-246">(leave blank)</span></span>  <br/> |<span data-ttu-id="15d9d-247">TXT</span><span class="sxs-lookup"><span data-stu-id="15d9d-247">TXT</span></span>  <br/> |<span data-ttu-id="15d9d-248">3600 (초)</span><span class="sxs-lookup"><span data-stu-id="15d9d-248">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="15d9d-249">"v = spf1 include:"-all "</span><span class="sxs-lookup"><span data-stu-id="15d9d-249">"v=spf1 include:spf.protection.outlook.com -all"</span></span>  <br/> <span data-ttu-id="15d9d-250">**참고:** 모든 공백이 올바르게 유지 되도록이 항목을 복사 하 여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-250">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Netregistry_SPF-TXTvalues](../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. <span data-ttu-id="15d9d-252">**레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-252">Select **Add Record**.</span></span>
    
    ![Netregistry_SPF-TXTvalues_AddRecord](../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="15d9d-254">Office 365에 필요한 2개의 SRV 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="15d9d-254">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="15d9d-255"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="15d9d-255"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="15d9d-256">시작 하려면 [이 링크](https://theconsole.netregistry.com.au/)를 사용 하 여 netregistry의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-256">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="15d9d-257">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="15d9d-257">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. <span data-ttu-id="15d9d-259">관리할 도메인 옆에 있는 **관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-259">Next to the domain you want to manage, select  **Manage**.</span></span>
    
    ![Netregistry_Manage](../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. <span data-ttu-id="15d9d-261">**영역 관리자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-261">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. <span data-ttu-id="15d9d-263">**영역 레코드 추가**아래의 목록에서 **SRV 레코드** 를 선택 하 고 **새 레코드 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-263">Under  **Add a zone record**, choose **SRV Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_SRV_select](../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. <span data-ttu-id="15d9d-265">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="15d9d-265">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="15d9d-266">이름 필드는 서비스 (예: _sip)와 프로토콜 (예: _tls)의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-266">The Name field is a combination of the service (for example, _sip) and protocol (for example, _tls).</span></span> 
  
    |<span data-ttu-id="15d9d-267">**유형**</span><span class="sxs-lookup"><span data-stu-id="15d9d-267">**Type**</span></span>|<span data-ttu-id="15d9d-268">**이름**</span><span class="sxs-lookup"><span data-stu-id="15d9d-268">**Name**</span></span>|<span data-ttu-id="15d9d-269">**TTL (초)**</span><span class="sxs-lookup"><span data-stu-id="15d9d-269">**TTL (SEC)**</span></span>|<span data-ttu-id="15d9d-270">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="15d9d-270">**Priority**</span></span>|<span data-ttu-id="15d9d-271">**가중치**</span><span class="sxs-lookup"><span data-stu-id="15d9d-271">**Weight**</span></span>|<span data-ttu-id="15d9d-272">**포트**</span><span class="sxs-lookup"><span data-stu-id="15d9d-272">**Port**</span></span>|<span data-ttu-id="15d9d-273">**대상**</span><span class="sxs-lookup"><span data-stu-id="15d9d-273">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="15d9d-274">SRV (서비스)</span><span class="sxs-lookup"><span data-stu-id="15d9d-274">SRV (service)</span></span>  <br/> |<span data-ttu-id="15d9d-275">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="15d9d-275">_sip._tls</span></span>  <br/> |<span data-ttu-id="15d9d-276">3600 (초)</span><span class="sxs-lookup"><span data-stu-id="15d9d-276">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="15d9d-277">100</span><span class="sxs-lookup"><span data-stu-id="15d9d-277">100</span></span>  <br/> |<span data-ttu-id="15d9d-278">개</span><span class="sxs-lookup"><span data-stu-id="15d9d-278">1</span></span>  <br/> |<span data-ttu-id="15d9d-279">443</span><span class="sxs-lookup"><span data-stu-id="15d9d-279">443</span></span>  <br/> |<span data-ttu-id="15d9d-280">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="15d9d-280">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="15d9d-281">SRV (서비스)</span><span class="sxs-lookup"><span data-stu-id="15d9d-281">SRV (service)</span></span>  <br/> |<span data-ttu-id="15d9d-282">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="15d9d-282">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="15d9d-283">3600 (초)</span><span class="sxs-lookup"><span data-stu-id="15d9d-283">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="15d9d-284">100</span><span class="sxs-lookup"><span data-stu-id="15d9d-284">100</span></span>  <br/> |<span data-ttu-id="15d9d-285">개</span><span class="sxs-lookup"><span data-stu-id="15d9d-285">1</span></span>  <br/> |<span data-ttu-id="15d9d-286">5061</span><span class="sxs-lookup"><span data-stu-id="15d9d-286">5061</span></span>  <br/> |<span data-ttu-id="15d9d-287">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="15d9d-287">sipfed.online.lync.com</span></span>  <br/> |
       
    ![Netregistry_SRV_values](../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. <span data-ttu-id="15d9d-289">**레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-289">Select **Add Record**.</span></span>
    
    ![Netregistry_SRV_values_AddRecord](../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. <span data-ttu-id="15d9d-291">이전 단계를 반복 하 여 다른 SRV 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-291">Repeat the previous steps to create the other SRV record.</span></span>
    
    <span data-ttu-id="15d9d-292">위 표에 있는 두 번째 행의 값을 두 번째 레코드의 상자에 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="15d9d-292">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="15d9d-p113">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="15d9d-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

