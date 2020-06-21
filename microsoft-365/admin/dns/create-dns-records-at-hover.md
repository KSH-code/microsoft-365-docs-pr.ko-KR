---
title: Microsoft에 대해 가리키기에서 DNS 레코드 만들기
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스를 위한 DNS 레코드를 설정 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: e51cb77831f4e29ac3a51602a1bb19f8b0c9e0e3
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780352"
---
# <a name="create-dns-records-at-hover-for-microsoft"></a><span data-ttu-id="b5688-103">Microsoft에 대해 가리키기에서 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="b5688-103">Create DNS records at Hover for Microsoft</span></span>

 <span data-ttu-id="b5688-104">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="b5688-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b5688-105">DNS 호스팅 공급자로 Hover를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-105">If Hover is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
     
<span data-ttu-id="b5688-106">지점에서 이러한 레코드를 추가 하 고 나면 도메인이 Microsoft 서비스에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-106">After you add these records at Hover, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="b5688-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="b5688-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="b5688-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="b5688-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="b5688-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b5688-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b5688-110">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="b5688-110">Add a TXT record for verification</span></span>
<span data-ttu-id="b5688-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="b5688-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="b5688-112">Before you use your domain with Microsoft, we have to make sure that you own it.</span><span class="sxs-lookup"><span data-stu-id="b5688-112">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="b5688-113">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span><span class="sxs-lookup"><span data-stu-id="b5688-113">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b5688-114">This record is used only to verify that you own your domain; it doesn't affect anything else.</span><span class="sxs-lookup"><span data-stu-id="b5688-114">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> <span data-ttu-id="b5688-115">You can delete it later, if you like.</span><span class="sxs-lookup"><span data-stu-id="b5688-115">You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="b5688-116">아래 단계를 따르거나 [비디오를 시청하세요](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span><span class="sxs-lookup"><span data-stu-id="b5688-116">Follow the steps below or [watch the video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span></span>
  
1. <span data-ttu-id="b5688-117">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span><span class="sxs-lookup"><span data-stu-id="b5688-117">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span></span> <span data-ttu-id="b5688-118">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="b5688-118">You'll be prompted to sign in.</span></span>
    
    ![로그인](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="b5688-120">**도메인 관리**에서 편집 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-120">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![도메인 선택](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="b5688-122">**DNS** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-122">Select the **DNS** tab.</span></span> 
    
    ![DNS 탭을 선택 합니다.](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="b5688-124">**새로 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-124">Select **Add New**.</span></span>
    
    ![새로 추가를 선택 합니다.](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="b5688-126">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b5688-126">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="b5688-127">Hostname(호스트 이름)</span><span class="sxs-lookup"><span data-stu-id="b5688-127">Hostname</span></span>  <br/> |<span data-ttu-id="b5688-128">레코드 종류</span><span class="sxs-lookup"><span data-stu-id="b5688-128">Record Type</span></span>  <br/> |<span data-ttu-id="b5688-129">Value(값)</span><span class="sxs-lookup"><span data-stu-id="b5688-129">Value</span></span>  <br/> |
    |@  <br/> |<span data-ttu-id="b5688-130">TXT</span><span class="sxs-lookup"><span data-stu-id="b5688-130">TXT</span></span>  <br/> |<span data-ttu-id="b5688-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b5688-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="b5688-132">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-132">**Note:** This is an example.</span></span> <span data-ttu-id="b5688-133">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="b5688-134">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="b5688-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![DNS 값을 입력 하거나 복사 하 여 붙여넣기](../../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. <span data-ttu-id="b5688-136">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-136">Select **Save**.</span></span>
    
    ![저장을 선택](../../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. <span data-ttu-id="b5688-138">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b5688-139">이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft 365로 돌아가서 Microsoft 365에 레코드를 찾을 것을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="b5688-140">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b5688-141">Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-141">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="b5688-142">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="b5688-143">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-143">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="b5688-144">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-144">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="b5688-145">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="b5688-145">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="b5688-146">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="b5688-146">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="b5688-147">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b5688-147">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="b5688-148">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="b5688-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="b5688-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="b5688-149"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="b5688-150">아래 단계를 따르거나 [비디오를 시청하세요](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span><span class="sxs-lookup"><span data-stu-id="b5688-150">Follow the steps below or [watch the video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span></span>
  
1. <span data-ttu-id="b5688-151">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span><span class="sxs-lookup"><span data-stu-id="b5688-151">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span></span> <span data-ttu-id="b5688-152">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="b5688-152">You'll be prompted to sign in.</span></span>
    
    ![로그인](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="b5688-154">**도메인 관리**에서 편집 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-154">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![도메인 선택](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="b5688-156">**DNS** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-156">Select the **DNS** tab.</span></span> 
    
    ![DNS 탭을 선택 합니다.](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="b5688-158">**새로 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-158">Select **Add New**.</span></span>
    
    ![새로 추가를 선택 합니다.](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="b5688-160">새 레코드의 상자에서 **레코드 종류**에 **MX**를 선택한 후 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-160">In the boxes for the new record, select **MX** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="b5688-161">**Hostname(호스트 이름)**</span><span class="sxs-lookup"><span data-stu-id="b5688-161">**Hostname**</span></span>|<span data-ttu-id="b5688-162">**Record Type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="b5688-162">**Record Type**</span></span>|<span data-ttu-id="b5688-163">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="b5688-163">**Priority**</span></span>|<span data-ttu-id="b5688-164">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="b5688-164">**Hostname**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="b5688-165">MX</span><span class="sxs-lookup"><span data-stu-id="b5688-165">MX</span></span>  <br/> |<span data-ttu-id="b5688-166">개</span><span class="sxs-lookup"><span data-stu-id="b5688-166">0</span></span>  <br/> <span data-ttu-id="b5688-167">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b5688-167">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="b5688-168">*\<domain-key\>*. mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b5688-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="b5688-169">**참고:** *\<domain-key\>* Microsoft 계정에서를 다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="b5688-169">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="b5688-170">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="b5688-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![DNS 값을 입력 하거나 복사 하 여 붙여넣기](../../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. <span data-ttu-id="b5688-172">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-172">Select **Save**.</span></span>
    
    ![저장을 선택](../../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. <span data-ttu-id="b5688-174">다른 MX 레코드가 있으면 다음 2단계 절차를 사용하여 각 레코드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-174">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="b5688-175">먼저 제거 하려는 레코드를 두고 **삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-175">First, mousing over a record that you want to remove, select **Delete**.</span></span>
    
    ![마우스를 위로 가져가면 삭제를 선택 합니다.](../../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    <span data-ttu-id="b5688-177">두 번째로, **예** 를 선택 하 여 삭제를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-177">Second, select **Yes** to confirm each deletion.</span></span> 
    
    ![삭제를 확인 하려면 예를 선택 합니다.](../../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    <span data-ttu-id="b5688-179">이 절차의 앞부분에서 추가한 레코드를 제외한 모든 MX 레코드가 제거될 때까지 이 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-179">Repeat this process until you have deleted all MX records except for the one that you added earlier in this procedure.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="b5688-180">Microsoft에 필요한 CNAME 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="b5688-180">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="b5688-181"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="b5688-181"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="b5688-182">아래 단계를 따르거나 [비디오를 시청하세요](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span><span class="sxs-lookup"><span data-stu-id="b5688-182">Follow the steps below or [watch the video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span></span>
  
1. <span data-ttu-id="b5688-183">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span><span class="sxs-lookup"><span data-stu-id="b5688-183">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span></span> <span data-ttu-id="b5688-184">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="b5688-184">You'll be prompted to sign in.</span></span>
    
    ![로그인](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="b5688-186">**도메인 관리**에서 편집 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-186">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![도메인 선택](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="b5688-188">**DNS** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-188">Select the **DNS** tab.</span></span> 
    
    ![DNS 탭을 선택 합니다.](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="b5688-190">6개의 CNAME 레코드 중 첫 번째 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-190">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="b5688-191">**새로 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-191">Select **Add New**.</span></span>
    
    ![새로 추가를 선택 합니다.](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="b5688-193">새 레코드의 빈 상자에서 **레코드 종류**로 **CNAME**을 선택한 후 다음 표의 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-193">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="b5688-194">**Hostname(호스트 이름)**</span><span class="sxs-lookup"><span data-stu-id="b5688-194">**Hostname**</span></span>|<span data-ttu-id="b5688-195">**Record Type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="b5688-195">**Record Type**</span></span>|<span data-ttu-id="b5688-196">**대상 호스트**</span><span class="sxs-lookup"><span data-stu-id="b5688-196">**Target Host**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="b5688-197">autodiscover</span><span class="sxs-lookup"><span data-stu-id="b5688-197">autodiscover</span></span>  <br/> |<span data-ttu-id="b5688-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="b5688-198">CNAME</span></span>  <br/> |<span data-ttu-id="b5688-199">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b5688-199">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="b5688-200">sip</span><span class="sxs-lookup"><span data-stu-id="b5688-200">sip</span></span>  <br/> |<span data-ttu-id="b5688-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="b5688-201">CNAME</span></span>  <br/> |<span data-ttu-id="b5688-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b5688-202">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="b5688-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="b5688-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="b5688-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="b5688-204">CNAME</span></span>  <br/> |<span data-ttu-id="b5688-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b5688-205">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="b5688-206">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="b5688-206">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="b5688-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="b5688-207">CNAME</span></span>  <br/> |<span data-ttu-id="b5688-208">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="b5688-208">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="b5688-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="b5688-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="b5688-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="b5688-210">CNAME</span></span>  <br/> |<span data-ttu-id="b5688-211">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b5688-211">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![DNS 값을 입력 하거나 복사 하 여 붙여넣기](../../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. <span data-ttu-id="b5688-213">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-213">Select **Save**.</span></span>
    
    ![저장을 선택](../../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. <span data-ttu-id="b5688-215">앞의 세 가지 단계와 표의 나머지 5개 행에 있는 값을 사용하여 나머지 5개의 CNAME 레코드를 각각 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-215">Using the preceding three steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="b5688-216">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="b5688-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="b5688-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="b5688-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b5688-218">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="b5688-219">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="b5688-220">도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="b5688-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="b5688-221">대신, 두 값 집합을 모두 포함 하는 *단일* SPF 레코드가 있도록 현재 레코드에 필수 Microsoft 값을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="b5688-222">아래 단계를 따르거나 [비디오를 시청하세요](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span><span class="sxs-lookup"><span data-stu-id="b5688-222">Follow the steps below or [watch the video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span></span>
  
1. <span data-ttu-id="b5688-223">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span><span class="sxs-lookup"><span data-stu-id="b5688-223">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span></span> <span data-ttu-id="b5688-224">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="b5688-224">You'll be prompted to sign in.</span></span>
    
    ![로그인](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="b5688-226">**도메인 관리**에서 편집 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-226">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![도메인 선택](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="b5688-228">**DNS** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-228">Select the **DNS** tab.</span></span> 
    
    ![DNS 탭을 선택 합니다.](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="b5688-230">**새로 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-230">Select **Add New**.</span></span>
    
    ![새로 추가를 선택 합니다.](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="b5688-232">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b5688-232">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="b5688-233">**Hostname(호스트 이름)**</span><span class="sxs-lookup"><span data-stu-id="b5688-233">**Hostname**</span></span>|<span data-ttu-id="b5688-234">**Record Type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="b5688-234">**Record Type**</span></span>|<span data-ttu-id="b5688-235">**값**</span><span class="sxs-lookup"><span data-stu-id="b5688-235">**Value**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="b5688-236">TXT</span><span class="sxs-lookup"><span data-stu-id="b5688-236">TXT</span></span>  <br/> |<span data-ttu-id="b5688-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="b5688-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="b5688-238">\*\*참고: \*\* 모든 간격이 올바르게 유지되도록 이 항목을 복사하여 붙여넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![DNS 값을 입력 하거나 복사 하 여 붙여넣기](../../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. <span data-ttu-id="b5688-240">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-240">Select **Save**.</span></span>
    
    ![저장을 선택](../../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="b5688-242">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="b5688-242">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="b5688-243"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="b5688-243"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="b5688-244">아래 단계를 따르거나 [비디오를 시청하세요](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span><span class="sxs-lookup"><span data-stu-id="b5688-244">Follow the steps below or [watch the video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span></span>
  
1. <span data-ttu-id="b5688-245">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span><span class="sxs-lookup"><span data-stu-id="b5688-245">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span></span> <span data-ttu-id="b5688-246">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="b5688-246">You'll be prompted to sign in.</span></span>
    
    ![로그인](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="b5688-248">**도메인 관리**에서 편집 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-248">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![도메인 선택](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="b5688-250">**DNS** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-250">Select the **DNS** tab.</span></span> 
    
    ![DNS 탭을 선택 합니다.](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="b5688-252">처음 2개의 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-252">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="b5688-253">**새로 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-253">Select **Add New**.</span></span>
    
    ![새로 추가를 선택 합니다.](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="b5688-255">새 레코드의 빈 상자에서 **레코드 종류**로 **SRV**를 선택한 후 다음 표의 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-255">In the empty boxes for the new record, select **SRV** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="b5688-256">**호스트 이름**</span><span class="sxs-lookup"><span data-stu-id="b5688-256">**Hostname**</span></span>|<span data-ttu-id="b5688-257">**Record Type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="b5688-257">**Record Type**</span></span>|<span data-ttu-id="b5688-258">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="b5688-258">**Priority**</span></span>|<span data-ttu-id="b5688-259">**Weight(가중치)**</span><span class="sxs-lookup"><span data-stu-id="b5688-259">**Weight**</span></span>|<span data-ttu-id="b5688-260">**Port(포트)**</span><span class="sxs-lookup"><span data-stu-id="b5688-260">**Port**</span></span>|<span data-ttu-id="b5688-261">**대상**</span><span class="sxs-lookup"><span data-stu-id="b5688-261">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b5688-262">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="b5688-262">_sip._tls</span></span>  <br/> |<span data-ttu-id="b5688-263">SRV</span><span class="sxs-lookup"><span data-stu-id="b5688-263">SRV</span></span>  <br/> |<span data-ttu-id="b5688-264">100</span><span class="sxs-lookup"><span data-stu-id="b5688-264">100</span></span>  <br/> |<span data-ttu-id="b5688-265">1 </span><span class="sxs-lookup"><span data-stu-id="b5688-265">1</span></span>  <br/> |<span data-ttu-id="b5688-266">443</span><span class="sxs-lookup"><span data-stu-id="b5688-266">443</span></span>  <br/> |<span data-ttu-id="b5688-267">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b5688-267">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="b5688-268">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="b5688-268">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="b5688-269">SRV</span><span class="sxs-lookup"><span data-stu-id="b5688-269">SRV</span></span>  <br/> |<span data-ttu-id="b5688-270">100</span><span class="sxs-lookup"><span data-stu-id="b5688-270">100</span></span>  <br/> |<span data-ttu-id="b5688-271">1 </span><span class="sxs-lookup"><span data-stu-id="b5688-271">1</span></span>  <br/> |<span data-ttu-id="b5688-272">5061</span><span class="sxs-lookup"><span data-stu-id="b5688-272">5061</span></span>  <br/> |<span data-ttu-id="b5688-273">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b5688-273">sipfed.online.lync.com</span></span>  <br/> |
   
    ![DNS 값을 입력 하거나 복사 하 여 붙여넣기](../../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. <span data-ttu-id="b5688-275">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-275">Select **Save**.</span></span>
    
    ![저장을 선택](../../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. <span data-ttu-id="b5688-277">앞의 세 가지 단계와 표의 두 번째 행에 있는 값을 사용하여 나머지 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b5688-277">Using the preceding three steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b5688-278">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="b5688-278">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="b5688-279">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="b5688-279">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="b5688-280">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b5688-280">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
