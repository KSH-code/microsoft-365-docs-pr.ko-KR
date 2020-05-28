---
title: Google 도메인을 사용 하 여 Microsoft를 설정 하도록 이름 서버 변경
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
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca
description: Google 도메인에서 사용자 지정 도메인의 DNS 레코드를 관리 하도록 Microsoft를 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 65649632b5e28e97909d91ca3e04355375afe3ac
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400656"
---
# <a name="change-nameservers-to-set-up-microsoft-with-google-domains"></a><span data-ttu-id="79137-103">Google 도메인을 사용 하 여 Microsoft를 설정 하도록 이름 서버 변경</span><span class="sxs-lookup"><span data-stu-id="79137-103">Change nameservers to set up Microsoft with Google Domains</span></span>

 <span data-ttu-id="79137-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="79137-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="79137-105">Microsoft에서 DNS 레코드를 관리 하도록 하려면 다음 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="79137-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="79137-106">원하는 경우 [Google 도메인에서 모든 DNS 레코드를 관리할](create-dns-records-at-google-domains.md)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79137-106">(If you prefer, you can [manage all your DNS records at Google Domains](create-dns-records-at-google-domains.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="79137-107">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="79137-107">Add a TXT record for verification</span></span>

<span data-ttu-id="79137-p102">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79137-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="79137-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79137-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="79137-112">시작 하려면 [이 링크](https://domains.google.com/registrar)를 통해 Google 도메인의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="79137-112">To get started, go to your domains page at Google Domains via [this link](https://domains.google.com/registrar).</span></span> <span data-ttu-id="79137-113">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="79137-113">You'll be prompted to sign in.</span></span> <span data-ttu-id="79137-114">To do so:</span><span class="sxs-lookup"><span data-stu-id="79137-114">To do so:</span></span>
    
1. <span data-ttu-id="79137-115">**로그인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="79137-115">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="79137-116">로그인 자격 증명을 입력 하 고 다시 **로그인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="79137-116">Enter your login credentials and again select **Sign In**.</span></span>
    
2. <span data-ttu-id="79137-117">**Domains** (도메인) 페이지의 **domain (도메인** ) 섹션에서 편집 하려는 도메인에 대해 **DNS 구성을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="79137-117">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="79137-118">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="79137-118">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="79137-119">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="79137-119">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="79137-120">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="79137-120">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="79137-121">**이름**</span><span class="sxs-lookup"><span data-stu-id="79137-121">**Name**</span></span> <br/> |<span data-ttu-id="79137-122">**종류**</span><span class="sxs-lookup"><span data-stu-id="79137-122">**Type**</span></span> <br/> |<span data-ttu-id="79137-123">**TTL**</span><span class="sxs-lookup"><span data-stu-id="79137-123">**TTL**</span></span> <br/> |<span data-ttu-id="79137-124">**데이터**</span><span class="sxs-lookup"><span data-stu-id="79137-124">**Data**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="79137-125">TXT</span><span class="sxs-lookup"><span data-stu-id="79137-125">TXT</span></span>  <br/> |<span data-ttu-id="79137-126">1H</span><span class="sxs-lookup"><span data-stu-id="79137-126">1H</span></span>  <br/> |<span data-ttu-id="79137-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="79137-127">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="79137-128">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="79137-128">**Note:** This is an example.</span></span> <span data-ttu-id="79137-129">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="79137-129">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="79137-130">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="79137-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)       <br/>  |
   
4. <span data-ttu-id="79137-131">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79137-131">Select **Add**.</span></span>
    
5. <span data-ttu-id="79137-132">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="79137-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="79137-133">도메인 등록 기관 사이트에서 레코드를 추가 했으므로 이제 Microsoft로 이동 하 여 레코드 검색을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="79137-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="79137-134">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="79137-134">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="79137-135">Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="79137-135">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="79137-136">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79137-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="79137-137">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79137-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="79137-138">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79137-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="79137-139">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="79137-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="79137-140">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79137-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="79137-141">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79137-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="79137-142">도메인의 NS(이름 서버) 레코드 변경</span><span class="sxs-lookup"><span data-stu-id="79137-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="79137-143">Microsoft에서 도메인 설정을 완료 하려면 도메인 등록 기관에서 도메인의 NS 레코드를 Microsoft 기본 및 보조 이름 서버를 가리키도록 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="79137-143">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="79137-144">이렇게 하면 Microsoft에서 도메인의 DNS 레코드를 업데이트 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="79137-144">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="79137-145">전자 메일, 비즈니스용 Skype Online, 공개 웹 사이트가 사용자의 도메인을 사용하도록 모든 레코드가 자동으로 추가되고 모든 설정이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="79137-145">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="79137-146">Microsoft 이름 서버를 가리키도록 도메인의 NS 레코드를 변경 하면 현재 도메인에 연결 된 모든 서비스가 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="79137-146">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="79137-147">예를 들어 rob@ *your_domain* 와 같이 도메인으로 전송 되는 모든 전자 메일</span><span class="sxs-lookup"><span data-stu-id="79137-147">For example, all email sent to your domain (like rob@ *your_domain.*</span></span>  <span data-ttu-id="79137-148">com)이 변경 된 후 Microsoft로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79137-148">com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="79137-149">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span><span class="sxs-lookup"><span data-stu-id="79137-149">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span></span> <span data-ttu-id="79137-150">>이 섹션의 단계를 완료 한 후에는 다음 4 가지 이름 서버 나열 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79137-150">> When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span> 
  
1. <span data-ttu-id="79137-p110">시작하려면 [이 링크](https://domains.google.com/registrar)를 사용하여 Google Domains의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다. 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="79137-p110">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="79137-154">**로그인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="79137-154">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="79137-155">로그인 자격 증명을 입력 하 고 다시 **로그인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="79137-155">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="79137-156">**Domains** (도메인) 페이지의 **domain (도메인** ) 섹션에서 편집 하려는 도메인에 대해 **DNS 구성을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="79137-156">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="79137-157">**도메인** 페이지의 **이름 서버** 구역에서 **사용자 지정 이름 서버 사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79137-157">On the **Domains** page, in the **Name servers** section, select **Use custom name servers**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-1](../../media/e264bc05-5a56-4962-bcaf-e2d999f62278.png)
  
4. <span data-ttu-id="79137-159">현재 표시된 페이지에 이름 서버가 이미 나열되어 있는지 여부에 따라 다음 두 가지 절차 중 하나를 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="79137-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="79137-160">이미 나열된 이름 서버가 **없으면**[나열된 이름 서버가 없으면](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="79137-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="79137-161">이미 나열된 이름 서버가 **있으면**[이름 서버가 나열되어 있는 경우](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="79137-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="79137-162">나열된 이름 서버가 없으면</span><span class="sxs-lookup"><span data-stu-id="79137-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="79137-163">첫 번째 이름 서버를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="79137-163">Add the first nameserver.</span></span>
    
    <span data-ttu-id="79137-164">**Name servers**(이름 서버) 섹션의 **NAME SERVER**(이름 서버) 상자에 다음 표의 첫 번째 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="79137-164">In the **Name servers** section, in the **NAME SERVER** box, type or copy and paste the first value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="79137-165">**첫 번째 이름 서버**</span><span class="sxs-lookup"><span data-stu-id="79137-165">**First name server**</span></span> <br/> |<span data-ttu-id="79137-166">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="79137-166">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="79137-167">**두 번째 이름 서버**</span><span class="sxs-lookup"><span data-stu-id="79137-167">**Second name server**</span></span> <br/> |<span data-ttu-id="79137-168">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="79137-168">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="79137-169">**세 번째 이름 서버**</span><span class="sxs-lookup"><span data-stu-id="79137-169">**Third name server**</span></span> <br/> |<span data-ttu-id="79137-170">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="79137-170">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="79137-171">**네 번째 이름 서버**</span><span class="sxs-lookup"><span data-stu-id="79137-171">**Fourth name server**</span></span> <br/> |<span data-ttu-id="79137-172">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="79137-172">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google-Domains-Redelegate-1-2](../../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. <span data-ttu-id="79137-174">**+ (추가)** 컨트롤을 선택 하 여 빈 행을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="79137-174">Select the **+ (add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-3](../../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. <span data-ttu-id="79137-176">나머지 세 개의 이름 서버 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="79137-176">Add the other three Nameserver records.</span></span>
    
    <span data-ttu-id="79137-177">**사용자 지정 이름 서버 사용** 섹션에서 표의 다음 행 값을 사용 하 여 레코드를 만들고 **+ (추가)** 컨트롤을 선택 하 여 다른 행을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="79137-177">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+ (add)** control to add another row.</span></span> 
    
    <span data-ttu-id="79137-178">4개의 이름 서버 레코드를 모두 만들 때까지 이 과정을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="79137-178">Repeat this process until you have created all four Nameserver records.</span></span>
    
4. <span data-ttu-id="79137-179">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79137-179">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="79137-181">이름 서버 레코드 업데이트가 인터넷의 DNS 시스템 전체에 업데이트되기까지 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79137-181">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="79137-182">그러면 Microsoft 전자 메일 및 기타 서비스가 모두 도메인에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79137-182">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="79137-183">이름 서버가 나열되어 있는 경우</span><span class="sxs-lookup"><span data-stu-id="79137-183">If there ARE nameservers already listed</span></span>

1. <span data-ttu-id="79137-184">다른 이름 서버 나열 되어 있는 경우 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="79137-184">If there are any other nameservers listed, select **Edit**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="79137-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="79137-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="79137-186">(즉, **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**또는 **ns4.bdm.microsoftonline.com**로 이름이 지정 *되지* 않은 현재 이름 서버 삭제 합니다.)</span><span class="sxs-lookup"><span data-stu-id="79137-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Google-Domains-BP-Redelegate-1-6-1](../../media/fb45d120-55ab-42c2-bdb6-19b130c3c7db.png)
  
2. <span data-ttu-id="79137-188">이름 서버를 하나씩 선택하고 키보드에서 **Delete** 키를 눌러 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="79137-188">Delete each one by selecting it, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-6-2](../../media/524e64ad-56e6-4254-8a64-e4a4c3230f89.png)
  
3. <span data-ttu-id="79137-190">**이름 서버** 구역의 **이름 서버** 행에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="79137-190">Still in the **Name servers** section, in the **NAME SERVER** rows, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="79137-191">**첫 번째 이름 서버**</span><span class="sxs-lookup"><span data-stu-id="79137-191">**First name server**</span></span> <br/> |<span data-ttu-id="79137-192">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="79137-192">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="79137-193">**두 번째 이름 서버**</span><span class="sxs-lookup"><span data-stu-id="79137-193">**Second name server**</span></span> <br/> |<span data-ttu-id="79137-194">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="79137-194">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="79137-195">**세 번째 이름 서버**</span><span class="sxs-lookup"><span data-stu-id="79137-195">**Third name server**</span></span> <br/> |<span data-ttu-id="79137-196">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="79137-196">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="79137-197">**네 번째 이름 서버**</span><span class="sxs-lookup"><span data-stu-id="79137-197">**Fourth name server**</span></span> <br/> |<span data-ttu-id="79137-198">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="79137-198">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google-Domains-Redelegate-1-7](../../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. <span data-ttu-id="79137-200">**+ (추가)** 컨트롤을 선택 하 여 빈 행을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="79137-200">Select the **+(add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-8](../../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. <span data-ttu-id="79137-202">나머지 두 개의 이름 서버 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="79137-202">Add the other two Nameserver records.</span></span>
    
    <span data-ttu-id="79137-203">**사용자 지정 이름 서버 사용** 섹션에서 표의 다음 행 값을 사용 하 여 레코드를 만들고 **+ (추가)** 컨트롤을 선택 하 여 다른 행을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="79137-203">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+(add)** control to add another row.</span></span> 
    
    <span data-ttu-id="79137-204">4개의 이름 서버 레코드를 모두 만들 때까지 이 과정을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="79137-204">Repeat this process until you have created all four Nameserver records.</span></span>
    
6. <span data-ttu-id="79137-205">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79137-205">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="79137-207">이름 서버 레코드 업데이트가 인터넷의 DNS 시스템 전체에 업데이트되기까지 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79137-207">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="79137-208">그러면 Microsoft 전자 메일 및 기타 서비스가 모두 도메인에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79137-208">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
