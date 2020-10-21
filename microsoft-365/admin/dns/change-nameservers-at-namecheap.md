---
title: 이름 서버를 변경 하 여 Namecheap을 사용 하 여 Microsoft 설정
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
ms.assetid: 84f467f6-28cf-40f0-94d0-a2a27ddfc2e7
description: 'Microsoft에서 DNS 레코드를 관리 하도록 하려면 Namecheap을 사용 하 여 Microsoft 사용자 지정 도메인을 설정 하는 방법을 알아봅니다. '
ms.openlocfilehash: e305abb7768b286dbd24336c1dab39d919f9a0ac
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646454"
---
# <a name="change-nameservers-to-set-up-microsoft-with-namecheap"></a><span data-ttu-id="b98f3-103">이름 서버를 변경 하 여 Namecheap을 사용 하 여 Microsoft 설정</span><span class="sxs-lookup"><span data-stu-id="b98f3-103">Change nameservers to set up Microsoft with Namecheap</span></span>

 <span data-ttu-id="b98f3-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="b98f3-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="b98f3-105">Microsoft에서 DNS 레코드를 관리 하도록 하려면 다음 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="b98f3-106">원하는 경우 [모든 MICROSOFT DNS 레코드를 Namecheap에서 관리할](create-dns-records-at-namecheap.md)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-106">(If you prefer, you can [manage all your Microsoft DNS records at Namecheap](create-dns-records-at-namecheap.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b98f3-107">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="b98f3-107">Add a TXT record for verification</span></span>

1. <span data-ttu-id="b98f3-108">시작 하려면 [이 링크](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)를 사용 하 여 Namecheap의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-108">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="b98f3-109">로그인 하 고 계속 진행 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-109">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="b98f3-111">**랜딩** 페이지의 **계정**아래 드롭다운 목록에서 **도메인 목록을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-111">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="b98f3-113">**도메인 목록** 페이지에서 편집 하려는 도메인의 이름을 찾은 다음 **관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-113">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="b98f3-115">**고급 DNS**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-115">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="b98f3-117">**호스트 레코드** 섹션에서 **새 레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-117">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="b98f3-119">**형식** 드롭다운에서 **TXT 레코드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-119">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b98f3-120">**새 레코드 추가**를 선택 하면 **유형** 드롭다운이 자동으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-120">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span>
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. <span data-ttu-id="b98f3-122">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-122">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="b98f3-123">(드롭다운 목록에서 **TTL** 값을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="b98f3-123">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
|<span data-ttu-id="b98f3-124">**유형**</span><span class="sxs-lookup"><span data-stu-id="b98f3-124">**Type**</span></span>|<span data-ttu-id="b98f3-125">**호스트**</span><span class="sxs-lookup"><span data-stu-id="b98f3-125">**Host**</span></span>|<span data-ttu-id="b98f3-126">**Value(값)**</span><span class="sxs-lookup"><span data-stu-id="b98f3-126">**Value**</span></span>|<span data-ttu-id="b98f3-127">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b98f3-127">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b98f3-128">TXT</span><span class="sxs-lookup"><span data-stu-id="b98f3-128">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="b98f3-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b98f3-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="b98f3-130">**참고**:이는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-130">**Note**: This is an example.</span></span> <span data-ttu-id="b98f3-131">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="b98f3-132">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="b98f3-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="b98f3-133">30 분</span><span class="sxs-lookup"><span data-stu-id="b98f3-133">30 min</span></span>  <br/> |
   
   ![Namecheap-BP-Verify-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. <span data-ttu-id="b98f3-135">**변경 내용 저장** (확인 표시) 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-135">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. <span data-ttu-id="b98f3-137">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b98f3-138">도메인 등록 기관 사이트에서 레코드를 추가 했으므로 이제 Microsoft로 이동 하 여 레코드 검색을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="b98f3-139">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b98f3-140">I관리 센터에서 \*\* 설정 \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="b98f3-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="b98f3-141">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="b98f3-142">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-142">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="b98f3-143">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="b98f3-p104">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b98f3-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="b98f3-147">도메인의 NS(이름 서버) 레코드 변경</span><span class="sxs-lookup"><span data-stu-id="b98f3-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="b98f3-148">Microsoft에서 도메인 설정을 완료 하려면 도메인 등록 기관에서 도메인의 NS 레코드를 Microsoft 기본 및 보조 이름 서버를 가리키도록 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-148">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="b98f3-149">이렇게 하면 Microsoft에서 도메인의 DNS 레코드를 업데이트 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-149">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="b98f3-150">전자 메일, 비즈니스용 Skype Online, 공개 웹 사이트가 사용자의 도메인을 사용하도록 모든 레코드가 자동으로 추가되고 모든 설정이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-150">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="b98f3-151">Microsoft 이름 서버를 가리키도록 도메인의 NS 레코드를 변경 하면 현재 도메인에 연결 된 모든 서비스가 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-151">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="b98f3-152">예를 들어 도메인으로 전송 되는 모든 전자 메일 (rob@ *your_domain*  )이 변경 된 후 Microsoft로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-152">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="b98f3-153">이 섹션의 단계를 완료하면 다음과 같이 네 개의 이름 서버  *만*  나열됩니다. >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  다음 절차에는 원치 않는 기타 이름 서버를 목록에서 삭제하는 방법과  *올바른*  이름 서버가 목록에 아직 없는 경우 이를 추가하는 방법이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-153">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span></span> 
  
1. <span data-ttu-id="b98f3-154">시작 하려면 [이 링크](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)를 사용 하 여 Namecheap의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-154">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="b98f3-155">로그인 하 고 계속 진행 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-155">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="b98f3-157">**랜딩** 페이지의 **계정**아래 드롭다운 목록에서 **도메인 목록을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-157">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="b98f3-159">**도메인 목록** 페이지에서 편집 하려는 도메인의 이름을 찾은 다음 **관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-159">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="b98f3-161">**도메인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-161">Select **Domain**.</span></span>
    
    ![Namecheap-BP-Redelegate-1-1](../../media/59588406-794e-4ae4-8526-35e3111b5791.png)
  
5. <span data-ttu-id="b98f3-163">**이름 서버** 섹션을 찾은 다음 **Namecheap 기본** 드롭다운 목록에서 **사용자 지정** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-163">Find the **NAMESERVERS** section, and then select **Custom** from the **Namecheap Default** drop-down list.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-2](../../media/7df56295-fdb3-472f-9442-13f780c2c93e.png)
  
6. <span data-ttu-id="b98f3-165">현재 표시 된 페이지에 이미 이름 서버 나열 되어 있는지 여부에 따라 다음 두 가지 절차 중 하나를 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-165">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="b98f3-166">나열된 이름 서버가 없으면</span><span class="sxs-lookup"><span data-stu-id="b98f3-166">If there are NO nameservers already listed</span></span>
<span data-ttu-id="b98f3-167"><a name="BKMK_ProcedureWithOUT"> </a></span><span class="sxs-lookup"><span data-stu-id="b98f3-167"><a name="BKMK_ProcedureWithOUT"> </a></span></span>

1. <span data-ttu-id="b98f3-168">이름 서버 **추가** 를 두 번 선택 하 여 두 개의 새 행을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-168">Select **ADD NAMESERVER** twice to add two new rows.</span></span>
    
    ![Namecheap-BP-Redelegate-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
2. <span data-ttu-id="b98f3-170">이름 서버 **상자에서** 다음 표의 값을 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-170">In the **Nameserver** boxes, type or copy and paste the values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="b98f3-171">**이름 서버 1**</span><span class="sxs-lookup"><span data-stu-id="b98f3-171">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="b98f3-172">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b98f3-172">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b98f3-173">**이름 서버 2**</span><span class="sxs-lookup"><span data-stu-id="b98f3-173">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="b98f3-174">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b98f3-174">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b98f3-175">**이름 서버 3**</span><span class="sxs-lookup"><span data-stu-id="b98f3-175">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="b98f3-176">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b98f3-176">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b98f3-177">**이름 서버 4**</span><span class="sxs-lookup"><span data-stu-id="b98f3-177">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="b98f3-178">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b98f3-178">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Namecheap-BP-Redelegate-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
3. <span data-ttu-id="b98f3-180">**저장** (확인 표시) 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-180">Select the **Save** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> <span data-ttu-id="b98f3-182">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="b98f3-182">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="b98f3-183">그러면 Microsoft 전자 메일 및 기타 서비스가 모두 도메인에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-183">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="b98f3-184">이름 서버가 나열되어 있는 경우</span><span class="sxs-lookup"><span data-stu-id="b98f3-184">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="b98f3-p109">네 개의  *올바른*  이름 서버 외에 기존 이름 서버가 있는 경우에  *만*  다음 단계를 따릅니다(즉, 이름이 *ns1.bdm.microsoftonline.com*, *ns2.bdm.microsoftonline.com*, **ns3.bdm.microsoftonline.com** 또는 **ns4.bdm.microsoftonline.com** 이  **아닌**  현재 모든 이름 서버  **만**  삭제).</span><span class="sxs-lookup"><span data-stu-id="b98f3-p109">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="b98f3-187">이름 서버 상자에 다른 이름 서버 나열 되어 있으면 하나씩 선택 하 고 키보드에서 **delete** 키를 눌러 **삭제 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b98f3-187">If there are any other nameservers listed in the **Nameserver** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-4](../../media/3270603a-c4f4-40b7-acad-733d56e2f53c.png)
  
2. <span data-ttu-id="b98f3-189">이름 서버 **추가** 를 두 번 선택 하 여 두 개의 새 행을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-189">Select **ADD NAMESERVER** twice to add two new rows.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
3. <span data-ttu-id="b98f3-191">이름 서버 **상자에서** 다음 표의 값을 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-191">In the **Nameserver** boxes, type or copy and paste the values from the following table.</span></span>
 
    
|||
|:-----|:-----|
|<span data-ttu-id="b98f3-192">**이름 서버 1**</span><span class="sxs-lookup"><span data-stu-id="b98f3-192">**Name Server 1**</span></span> <br/> |<span data-ttu-id="b98f3-193">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b98f3-193">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b98f3-194">**이름 서버 2**</span><span class="sxs-lookup"><span data-stu-id="b98f3-194">**Name Server 2**</span></span> <br/> |<span data-ttu-id="b98f3-195">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b98f3-195">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b98f3-196">**이름 서버 3**</span><span class="sxs-lookup"><span data-stu-id="b98f3-196">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="b98f3-197">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b98f3-197">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b98f3-198">**이름 서버 4**</span><span class="sxs-lookup"><span data-stu-id="b98f3-198">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="b98f3-199">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b98f3-199">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Namecheap-BP-Redelegate-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
4. <span data-ttu-id="b98f3-201">**저장** (확인 표시) 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-201">Select the **Save** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> <span data-ttu-id="b98f3-203">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="b98f3-203">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="b98f3-204">그러면 Microsoft 전자 메일 및 기타 서비스가 모두 도메인에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b98f3-204">Then your Microsoft email and other services will be all set to work with your domain.</span></span>
