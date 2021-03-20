---
title: Microsoft용 네트워크 솔루션에서 DNS 레코드 만들기
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
ms.assetid: 1dc55f9f-5309-450f-acc3-b2b4119c8be3
description: Microsoft용 네트워크 솔루션에서 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대한 DNS 레코드를 설정하는 방법을 알아보십시오.
ms.openlocfilehash: f25e21037695c99489adc9038bf70629a103ec7a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910141"
---
# <a name="create-dns-records-at-network-solutions-for-microsoft"></a><span data-ttu-id="66bef-103">Microsoft용 네트워크 솔루션에서 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="66bef-103">Create DNS records at Network Solutions for Microsoft</span></span>

 <span data-ttu-id="66bef-104">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.yml)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="66bef-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="66bef-105">DNS 호스팅 공급자로 Network Solutions를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-105">If Network Solutions is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="66bef-106">다음은 추가할 기본 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-106">These are the main records to add.</span></span> <span data-ttu-id="66bef-107">아래 단계를 따르거나 [비디오를 시청하세요](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span><span class="sxs-lookup"><span data-stu-id="66bef-107">Follow the steps below or [watch the video](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span> 
  
- [<span data-ttu-id="66bef-108">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="66bef-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="66bef-109">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="66bef-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="66bef-110">Microsoft에 필요한 CNAME 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="66bef-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="66bef-111">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="66bef-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="66bef-112">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="66bef-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="66bef-113">네트워크 솔루션에서 이러한 레코드를 추가하고 나면 도메인이 Microsoft 서비스에서 작동할 수 있도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-113">After you add these records at Network Solutions, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="66bef-p102">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66bef-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="66bef-117">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="66bef-117">Add a TXT record for verification</span></span>
<span data-ttu-id="66bef-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="66bef-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="66bef-p103">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="66bef-p104">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="66bef-123">아래 단계를 따르거나 [비디오를 시청하세요(0:47에 시작)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span><span class="sxs-lookup"><span data-stu-id="66bef-123">Follow the steps below or [watch the video (start at 0:47)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span>
  
1. <span data-ttu-id="66bef-p105">시작하려면 [이 링크](https://www.networksolutions.com/manage-it)를 사용하여 Network Solutions의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-p105">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="66bef-126">로그인 **단추를 선택하기** 전에  먼저 로그인 **대상:** 드롭다운 목록에서 내 도메인 이름 관리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-126">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Manage My Domain Names(내 도메인 이름 관리)를 선택하고 Network Solutions에 로그인합니다.](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="66bef-128">수정하려는 도메인 이름 옆의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-128">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![도메인에 대한 확인란을 선택합니다.](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="66bef-130">DNS **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-130">Select **Edit DNS**.</span></span>
    
    ![DNS 편집을 선택합니다.](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="66bef-132">고급 **DNS 레코드 관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-132">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="66bef-133">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="66bef-133">(You may have to scroll down.)</span></span>
    
    ![고급 DNS 레코드 관리 선택](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="66bef-135">아래로 스크롤하여 **텍스트(TXT 레코드)** 구역으로 이동한 다음 **TXT 레코드 편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-135">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Select Edit TXT Records](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="66bef-137">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-137">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
    |<span data-ttu-id="66bef-138">**Host**</span><span class="sxs-lookup"><span data-stu-id="66bef-138">**Host**</span></span>|<span data-ttu-id="66bef-139">**TTL**</span><span class="sxs-lookup"><span data-stu-id="66bef-139">**TTL**</span></span>|<span data-ttu-id="66bef-140">**텍스트**</span><span class="sxs-lookup"><span data-stu-id="66bef-140">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="66bef-141">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="66bef-141">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="66bef-142">3600</span><span class="sxs-lookup"><span data-stu-id="66bef-142">3600</span></span>  <br/> |<span data-ttu-id="66bef-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="66bef-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="66bef-144">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-144">**Note:** This is an example.</span></span> <span data-ttu-id="66bef-145">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-145">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="66bef-146">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="66bef-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![새 레코드의 상자에 값을 입력하거나 붙여넣습니다.](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="66bef-148">계속을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-148">Select **Continue**.</span></span>
    
    ![계속을 선택합니다.](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="66bef-150">변경 **내용 저장을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-150">Select **Save Changes**.</span></span>
    
    ![변경 내용 저장 선택](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="66bef-152">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-152">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="66bef-153">이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-153">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="66bef-154">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-154">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="66bef-155">I관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인</a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="66bef-155">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="66bef-156">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-156">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="66bef-157">**설정** 페이지에서 **설정 시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-157">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="66bef-158">**도메인 확인** 페이지에서 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-158">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="66bef-p107">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66bef-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="66bef-162">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="66bef-162">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="66bef-163"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="66bef-163"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="66bef-164">아래 단계를 따르거나 [비디오를 시청하세요(3:51에 시작)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span><span class="sxs-lookup"><span data-stu-id="66bef-164">Follow the steps below or [watch the video (start at 3:51)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span>
  
1. <span data-ttu-id="66bef-p108">시작하려면 [이 링크](https://www.networksolutions.com/manage-it)를 사용하여 Network Solutions의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-p108">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="66bef-167">로그인 **단추를 선택하기** 전에  먼저 로그인 **대상:** 드롭다운 목록에서 내 도메인 이름 관리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-167">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Manage My Domain Names(내 도메인 이름 관리)를 선택하고 Network Solutions에 로그인합니다.](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="66bef-169">수정하려는 도메인 이름 옆의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-169">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![도메인에 대한 확인란을 선택합니다.](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="66bef-171">DNS **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-171">Select **Edit DNS**.</span></span>
    
    ![DNS 편집을 선택합니다.](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="66bef-173">고급 **DNS 레코드 관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-173">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="66bef-174">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="66bef-174">(You may have to scroll down.)</span></span>
    
    ![고급 DNS 레코드 관리 선택](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="66bef-176">아래로 스크롤하여 **메일 서버(MX 레코드)** 구역으로 이동한 다음 MX 레코드 **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-176">Scroll down to the **Mail Servers (MX Records)** section, and then select **Edit MX Records**.</span></span>
    
    ![MX 레코드 편집 선택](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. <span data-ttu-id="66bef-178">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-178">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="66bef-179">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="66bef-179">**Priority**</span></span>|<span data-ttu-id="66bef-180">**TTL**</span><span class="sxs-lookup"><span data-stu-id="66bef-180">**TTL**</span></span>|<span data-ttu-id="66bef-181">**메일 서버**</span><span class="sxs-lookup"><span data-stu-id="66bef-181">**Mail Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="66bef-182">10  </span><span class="sxs-lookup"><span data-stu-id="66bef-182">10</span></span>  <br/> <span data-ttu-id="66bef-183">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](../setup/domains-faq.yml)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66bef-183">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |<span data-ttu-id="66bef-184">3600</span><span class="sxs-lookup"><span data-stu-id="66bef-184">3600</span></span>  <br/> | <span data-ttu-id="66bef-185">*\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="66bef-185">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="66bef-186">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-186">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="66bef-187">**참고:** Microsoft  *\<domain-key\>*  계정에서 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="66bef-187">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span> [<span data-ttu-id="66bef-188">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="66bef-188">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![새 레코드의 상자에 값을 입력하거나 붙여넣습니다.](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. <span data-ttu-id="66bef-190">계속을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-190">Select **Continue**.</span></span>
    
    ![계속을 선택합니다.](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. <span data-ttu-id="66bef-192">변경 **내용 저장을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-192">Select **Save Changes**.</span></span>
    
    ![변경 내용 저장 선택](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. <span data-ttu-id="66bef-194">다른 MX 레코드가 있으면 각 레코드에 대한 **삭제** 를 선택하여 레코드를 모두 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-194">If there are any other MX records, delete all of them by selecting **Delete** for each record.</span></span> 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. <span data-ttu-id="66bef-196">모두 선택되면 계속 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-196">When they are all selected, select **Continue**.</span></span>
    
    ![계속을 선택합니다.](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. <span data-ttu-id="66bef-198">변경 **내용 저장을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-198">Select **Save Changes**.</span></span>
    
    ![변경 내용 저장 선택](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="66bef-200">Microsoft에 필요한 CNAME 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="66bef-200">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="66bef-201"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="66bef-201"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="66bef-202">아래 단계를 따르거나 [비디오를 시청하세요(4:43에 시작)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span><span class="sxs-lookup"><span data-stu-id="66bef-202">Follow the steps below or [watch the video (start at 4:43)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span>
  
1. <span data-ttu-id="66bef-p110">시작하려면 [이 링크](https://www.networksolutions.com/manage-it)를 사용하여 Network Solutions의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-p110">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="66bef-205">로그인 **단추를 선택하기** 전에  먼저 로그인 **대상:** 드롭다운 목록에서 내 도메인 이름 관리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-205">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Manage My Domain Names(내 도메인 이름 관리)를 선택하고 Network Solutions에 로그인합니다.](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="66bef-207">수정하려는 도메인 이름 옆의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-207">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![도메인에 대한 확인란을 선택합니다.](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="66bef-209">DNS **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-209">Select **Edit DNS**.</span></span>
    
    ![DNS 편집을 선택합니다.](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="66bef-211">고급 **DNS 레코드 관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-211">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="66bef-212">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="66bef-212">(You may have to scroll down.)</span></span>
    
    ![고급 DNS 레코드 관리 선택](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="66bef-214">아래로 스크롤하여 **호스트 별칭(CNAME 레코드)** 구역으로 이동한 다음 **CNAME 레코드 편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-214">Scroll down to the **Host Aliases (CNAME Records)** section, and then select **Edit CNAME Records**.</span></span>
    
    ![호스트 별칭에서 CNAME 레코드 편집 선택](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. <span data-ttu-id="66bef-216">네 개의 새 레코드 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-216">In the boxes for the four new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="66bef-217">**별칭**</span><span class="sxs-lookup"><span data-stu-id="66bef-217">**Alias**</span></span>|<span data-ttu-id="66bef-218">**TTL**</span><span class="sxs-lookup"><span data-stu-id="66bef-218">**TTL**</span></span>|<span data-ttu-id="66bef-219">**호스트 이름 참조**</span><span class="sxs-lookup"><span data-stu-id="66bef-219">**Refers to Host Name**</span></span>|<span data-ttu-id="66bef-220">**기타 호스트          ( **기타 호스트** 옵션 단추 선택)**</span><span class="sxs-lookup"><span data-stu-id="66bef-220">**Other Host          (select the **Other Host** option button)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="66bef-221">autodiscover</span><span class="sxs-lookup"><span data-stu-id="66bef-221">autodiscover</span></span>  <br/> |<span data-ttu-id="66bef-222">3600</span><span class="sxs-lookup"><span data-stu-id="66bef-222">3600</span></span>  <br/> |<span data-ttu-id="66bef-223">(설정 없음)</span><span class="sxs-lookup"><span data-stu-id="66bef-223">(No setting)</span></span>  <br/> |<span data-ttu-id="66bef-224">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="66bef-224">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="66bef-225">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-225">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="66bef-226">sip</span><span class="sxs-lookup"><span data-stu-id="66bef-226">sip</span></span>  <br/> |<span data-ttu-id="66bef-227">3600</span><span class="sxs-lookup"><span data-stu-id="66bef-227">3600</span></span>  <br/> |<span data-ttu-id="66bef-228">(설정 없음)</span><span class="sxs-lookup"><span data-stu-id="66bef-228">(No setting)</span></span>  <br/> |<span data-ttu-id="66bef-229">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="66bef-229">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="66bef-230">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-230">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="66bef-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="66bef-231">lyncdiscover</span></span>  <br/> |<span data-ttu-id="66bef-232">3600</span><span class="sxs-lookup"><span data-stu-id="66bef-232">3600</span></span>  <br/> |<span data-ttu-id="66bef-233">(설정 없음)</span><span class="sxs-lookup"><span data-stu-id="66bef-233">(No setting)</span></span>  <br/> |<span data-ttu-id="66bef-234">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="66bef-234">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="66bef-235">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-235">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="66bef-236">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="66bef-236">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="66bef-237">3600</span><span class="sxs-lookup"><span data-stu-id="66bef-237">3600</span></span>  <br/> |<span data-ttu-id="66bef-238">(설정 없음)</span><span class="sxs-lookup"><span data-stu-id="66bef-238">(No setting)</span></span>  <br/> |<span data-ttu-id="66bef-239">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="66bef-239">enterpriseregistration.windows.net</span></span>  <br/> <span data-ttu-id="66bef-240">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-240">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="66bef-241">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="66bef-241">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="66bef-242">3600</span><span class="sxs-lookup"><span data-stu-id="66bef-242">3600</span></span>  <br/> |<span data-ttu-id="66bef-243">(설정 없음)</span><span class="sxs-lookup"><span data-stu-id="66bef-243">(No setting)</span></span>  <br/> |<span data-ttu-id="66bef-244">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="66bef-244">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> <span data-ttu-id="66bef-245">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-245">**This value MUST end with a period (.)**</span></span> <br/> |
    
    ![새 레코드의 값 입력 또는 붙여넣기](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. <span data-ttu-id="66bef-247">필요한 모든 CNAME 레코드를 추가한 경우 계속 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-247">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![계속을 선택합니다.](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. <span data-ttu-id="66bef-249">변경 **내용 저장을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-249">Select **Save Changes**.</span></span>
    
    ![변경 내용 저장 선택](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="66bef-251">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="66bef-251">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="66bef-252"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="66bef-252"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="66bef-253">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-253">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="66bef-254">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-254">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="66bef-255">도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="66bef-255">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="66bef-256">대신 두 값 집합을 모두 포함하는  *단일*  SPF 레코드가 있도록 현재 레코드에 필요한 Microsoft 값을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-256">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="66bef-257">아래 단계를 따르거나 [비디오를 시청하세요(5:35에 시작)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span><span class="sxs-lookup"><span data-stu-id="66bef-257">Follow the steps below or [watch the video (start at 5:35)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span>
  
1. <span data-ttu-id="66bef-p112">시작하려면 [이 링크](https://www.networksolutions.com/manage-it)를 사용하여 Network Solutions의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-p112">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="66bef-260">로그인 **단추를 선택하기** 전에  먼저 로그인 **대상:** 드롭다운 목록에서 내 도메인 이름 관리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-260">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Manage My Domain Names(내 도메인 이름 관리)를 선택하고 Network Solutions에 로그인합니다.](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="66bef-262">수정하려는 도메인 이름 옆의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-262">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![도메인에 대한 확인란을 선택합니다.](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="66bef-264">DNS **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-264">Select **Edit DNS**.</span></span>
    
    ![DNS 편집을 선택합니다.](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="66bef-266">고급 **DNS 레코드 관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-266">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="66bef-267">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="66bef-267">(You may have to scroll down.)</span></span>
    
    ![고급 DNS 레코드 관리 선택](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="66bef-269">아래로 스크롤하여 **텍스트(TXT 레코드)** 구역으로 이동한 다음 **TXT 레코드 편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-269">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![텍스트에서 TXT 레코드 편집 선택](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. <span data-ttu-id="66bef-271">새 레코드의 상자에서 다음 값을 입력하거나 복사하여 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-271">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="66bef-272">**호스트**</span><span class="sxs-lookup"><span data-stu-id="66bef-272">**Host**</span></span>|<span data-ttu-id="66bef-273">**TTL**</span><span class="sxs-lookup"><span data-stu-id="66bef-273">**TTL**</span></span>|<span data-ttu-id="66bef-274">**텍스트**</span><span class="sxs-lookup"><span data-stu-id="66bef-274">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="66bef-275">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="66bef-275">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="66bef-276">3600</span><span class="sxs-lookup"><span data-stu-id="66bef-276">3600</span></span>  <br/> |<span data-ttu-id="66bef-277">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="66bef-277">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="66bef-278">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-278">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span> |
       
    ![새 레코드의 값 입력 또는 붙여넣기](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. <span data-ttu-id="66bef-280">계속을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-280">Select **Continue**.</span></span>
    
    ![계속을 선택합니다.](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. <span data-ttu-id="66bef-282">변경 **내용 저장을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-282">Select **Save Changes**.</span></span>
    
    ![변경 내용 저장 선택](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="66bef-284">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="66bef-284">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="66bef-285"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="66bef-285"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="66bef-286">아래 단계를 따르거나 [비디오를 시청하세요(6:18에 시작)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span><span class="sxs-lookup"><span data-stu-id="66bef-286">Follow the steps below or [watch the video (start at 6:18)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span>
  
1. <span data-ttu-id="66bef-p113">시작하려면 [이 링크](https://www.networksolutions.com/manage-it)를 사용하여 Network Solutions의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-p113">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="66bef-289">로그인 **단추를 선택하기** 전에  먼저 로그인 **대상:** 드롭다운 목록에서 내 도메인 이름 관리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-289">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Manage My Domain Names(내 도메인 이름 관리)를 선택하고 Network Solutions에 로그인합니다.](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="66bef-291">수정하려는 도메인 이름 옆의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-291">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![도메인에 대한 확인란을 선택합니다.](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="66bef-293">DNS **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-293">Select **Edit DNS**.</span></span>
    
    ![DNS 편집을 선택합니다.](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="66bef-295">고급 **DNS 레코드 관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-295">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="66bef-296">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="66bef-296">(You may have to scroll down.)</span></span>
    
    ![고급 DNS 레코드 관리 선택](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="66bef-298">아래로 스크롤하여 **서비스(SRV 레코드)** 구역으로 이동한 다음 **SRV 레코드 편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-298">Scroll down to the **Service (SRV Records)** section, and then select **Edit SRV Records**.</span></span>
    
    ![서비스에서 SRV 레코드 편집 선택](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. <span data-ttu-id="66bef-300">두 개의 새 레코드 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="66bef-300">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="66bef-301">(드롭다운 목록에서 **서비스** 및 **프로토콜** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="66bef-301">(Choose the **Service** and **Protocol** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="66bef-302">**서비스**</span><span class="sxs-lookup"><span data-stu-id="66bef-302">**Service**</span></span>|<span data-ttu-id="66bef-303">**프로토콜**</span><span class="sxs-lookup"><span data-stu-id="66bef-303">**Protocol**</span></span>|<span data-ttu-id="66bef-304">**TTL**</span><span class="sxs-lookup"><span data-stu-id="66bef-304">**TTL**</span></span>|<span data-ttu-id="66bef-305">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="66bef-305">**Priority**</span></span>|<span data-ttu-id="66bef-306">**Weight(가중치)**</span><span class="sxs-lookup"><span data-stu-id="66bef-306">**Weight**</span></span>|<span data-ttu-id="66bef-307">**Port(포트)**</span><span class="sxs-lookup"><span data-stu-id="66bef-307">**Port**</span></span>|<span data-ttu-id="66bef-308">**대상**</span><span class="sxs-lookup"><span data-stu-id="66bef-308">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="66bef-309">_sip</span><span class="sxs-lookup"><span data-stu-id="66bef-309">_sip</span></span>  <br/> |<span data-ttu-id="66bef-310">_tls</span><span class="sxs-lookup"><span data-stu-id="66bef-310">_tls</span></span>  <br/> |<span data-ttu-id="66bef-311">3600</span><span class="sxs-lookup"><span data-stu-id="66bef-311">3600</span></span>  <br/> |<span data-ttu-id="66bef-312">100</span><span class="sxs-lookup"><span data-stu-id="66bef-312">100</span></span>  <br/> |<span data-ttu-id="66bef-313">1</span><span class="sxs-lookup"><span data-stu-id="66bef-313">1</span></span>  <br/> |<span data-ttu-id="66bef-314">443</span><span class="sxs-lookup"><span data-stu-id="66bef-314">443</span></span>  <br/> |<span data-ttu-id="66bef-315">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="66bef-315">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="66bef-316">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-316">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="66bef-317">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="66bef-317">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="66bef-318">_tcp</span><span class="sxs-lookup"><span data-stu-id="66bef-318">_tcp</span></span>  <br/> |<span data-ttu-id="66bef-319">3600</span><span class="sxs-lookup"><span data-stu-id="66bef-319">3600</span></span>  <br/> |<span data-ttu-id="66bef-320">100</span><span class="sxs-lookup"><span data-stu-id="66bef-320">100</span></span>  <br/> |<span data-ttu-id="66bef-321">1</span><span class="sxs-lookup"><span data-stu-id="66bef-321">1</span></span>  <br/> |<span data-ttu-id="66bef-322">5061</span><span class="sxs-lookup"><span data-stu-id="66bef-322">5061</span></span>  <br/> |<span data-ttu-id="66bef-323">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="66bef-323">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="66bef-324">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-324">**This value MUST end with a period (.)**</span></span> <br/> |
       
    ![새 레코드의 값 입력 또는 붙여넣기](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. <span data-ttu-id="66bef-326">계속을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-326">Select **Continue**.</span></span>
    
    ![계속을 선택합니다.](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. <span data-ttu-id="66bef-328">변경 **내용 저장을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="66bef-328">Select **Save Changes**.</span></span>
    
    ![변경 내용 저장 선택](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  <span data-ttu-id="66bef-p114">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66bef-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
