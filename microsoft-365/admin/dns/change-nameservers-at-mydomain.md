---
title: MyDomain을 사용 하 여 Microsoft를 설정 하도록 이름 서버 변경
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
ms.assetid: c5f6140a-4a12-401b-9bbd-7dfb0d6b0ba3
description: MyDomain에서 사용자 지정 도메인의 DNS 레코드를 관리 하도록 Microsoft를 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: d8fc61c3adbe8b5b865bd82b8c4e0944198921e7
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400632"
---
# <a name="change-nameservers-to-set-up-microsoft-with-mydomain"></a><span data-ttu-id="0446b-103">MyDomain을 사용 하 여 Microsoft를 설정 하도록 이름 서버 변경</span><span class="sxs-lookup"><span data-stu-id="0446b-103">Change nameservers to set up Microsoft with MyDomain</span></span>

 <span data-ttu-id="0446b-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="0446b-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="0446b-105">Microsoft에서 DNS 레코드를 관리 하도록 하려면 다음 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="0446b-106">원하는 경우 [모든 MICROSOFT DNS 레코드를 MyDomain에서 관리할](create-dns-records-at-mydomain.md)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-106">(If you prefer, you can [manage all your Microsoft DNS records at MyDomain](create-dns-records-at-mydomain.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="0446b-107">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="0446b-107">Add a TXT record for verification</span></span>

<span data-ttu-id="0446b-p102">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0446b-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="0446b-p104">시작하려면 [이 링크](https://www.mydomain.com/controlpanel)를 사용하여 MyDomain의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-p104">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0446b-114">**내 즐겨 찾기** 섹션에서 **도메인 센터**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-114">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="0446b-115">**도메인**에서 편집할 도메인 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-115">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="0446b-116">**개요** 행에서 **DNS**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-116">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="0446b-117">**수정** 드롭다운 목록에서 **TXT/SPF 레코드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-117">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="0446b-118">
            \*\*콘텐츠\*\* 아래의 새 레코드에 대한 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-118">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
||
|:-----|
|<span data-ttu-id="0446b-119">**콘텐츠**</span><span class="sxs-lookup"><span data-stu-id="0446b-119">**Content**</span></span> <br/> |
|<span data-ttu-id="0446b-120">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="0446b-120">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="0446b-121">**참고**:이는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-121">**Note**: This is an example.</span></span> <span data-ttu-id="0446b-122">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-122">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="0446b-123">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="0446b-123">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="0446b-124">**추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-124">Select **Add**.</span></span>
    
8. <span data-ttu-id="0446b-125">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-125">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="0446b-126">이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft 365로 돌아가서 Microsoft 365에 레코드를 찾을 것을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-126">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="0446b-127">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-127">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="0446b-128">Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-128">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="0446b-129">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-129">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="0446b-130">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-130">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="0446b-131">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-131">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0446b-132">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="0446b-132">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="0446b-133">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-133">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="0446b-134">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0446b-134">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="0446b-135">도메인의 NS(이름 서버) 레코드 변경</span><span class="sxs-lookup"><span data-stu-id="0446b-135">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="0446b-136">Microsoft에서 도메인 설정을 완료 하려면 도메인 등록 기관에서 도메인의 NS 레코드를 Microsoft 기본 및 보조 이름 서버를 가리키도록 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-136">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="0446b-137">이렇게 하면 Microsoft에서 도메인의 DNS 레코드를 업데이트 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-137">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="0446b-138">전자 메일, 비즈니스용 Skype Online, 공개 웹 사이트가 사용자의 도메인을 사용하도록 모든 레코드가 자동으로 추가되고 모든 설정이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-138">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="0446b-139">Microsoft 이름 서버를 가리키도록 도메인의 NS 레코드를 변경 하면 현재 도메인에 연결 된 모든 서비스가 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-139">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="0446b-140">예를 들어 rob@ *your_domain* 와 같이 도메인으로 전송 되는 모든 전자 메일</span><span class="sxs-lookup"><span data-stu-id="0446b-140">For example, all email sent to your domain (like rob@ *your_domain.*</span></span> <span data-ttu-id="0446b-141">com)이 변경 된 후 Microsoft로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-141">com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="0446b-142">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span><span class="sxs-lookup"><span data-stu-id="0446b-142">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span></span> <br/> <span data-ttu-id="0446b-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span><span class="sxs-lookup"><span data-stu-id="0446b-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span>
  
1. <span data-ttu-id="0446b-p110">시작하려면 [이 링크](https://www.mydomain.com/controlpanel)를 사용하여 MyDomain의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0446b-146">**내 즐겨 찾기** 섹션에서 **도메인 센터**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-146">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="0446b-147">**도메인**에서 편집할 도메인 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-147">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="0446b-148">**개요** 행에서 **이름 서버**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-148">In the **Overview** row, select **Nameservers**.</span></span>
    
    ![MyDomain-BP-Redelegate-1-1](../../media/49e91235-44b5-46d6-a82e-8f11329db3d6.png)
  
5. <span data-ttu-id="0446b-150">**Update Name Servers(이름 서버 업데이트)** 구역에서 **Use different name servers(다른 이름 서버 사용)** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-150">In the **Update Name Servers** section, select **Use different name servers**.</span></span>
    
    ![MyDomain-BP-Redelegate-1-2-1](../../media/f869fb26-54dc-4b66-8378-a78a79b582bd.png)
  
6. <span data-ttu-id="0446b-152">현재 표시 된 페이지에 이미 이름 서버 나열 되어 있는지 여부에 따라 다음 두 가지 절차 중 하나를 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-152">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-the-correct-nameservers-are-already-listed"></a><span data-ttu-id="0446b-153">올바른 이름 서버가 이미 나열되어 있으면</span><span class="sxs-lookup"><span data-stu-id="0446b-153">If the correct nameservers ARE already listed</span></span>

- <span data-ttu-id="0446b-154">올바른 이름 서버가 이미 나열되어 있으면 이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-154">If the correct nameservers are already listed, you can skip this step.</span></span>
    
    ![MyDomain-BP-Redelegate-1-2-2](../../media/601f6a46-15bd-4a92-b792-ac628ff86628.png)
  
### <a name="if-the-correct-nameservers-are-not-already-listed"></a><span data-ttu-id="0446b-156">올바른 이름 서버가 나열되어 있지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="0446b-156">If the correct nameservers are NOT already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="0446b-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="0446b-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="0446b-158">(즉, **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**또는 **ns4.bdm.microsoftonline.com**로 이름이 지정 *되지* 않은 현재 이름 서버 삭제 합니다.)</span><span class="sxs-lookup"><span data-stu-id="0446b-158">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="0446b-159">**Nameserver:**(이름 서버:) 필드에서 각 항목을 선택한 다음 키보드에서 **Delete** 키를 눌러 기존 이름 서버를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-159">Delete the existing nameservers by selecting each entry in the **Nameserver:** field, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![MyDomain-BP-Redelegate-1-3-1](../../media/5024cd27-a2b1-42a2-99e4-5ceb5e6eddb9.png)
  
2. <span data-ttu-id="0446b-161">**추가** 를 두 번 선택 하 여 새 이름 서버 행을 두 개 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-161">Select **Add More** twice to add two new Nameserver rows.</span></span> 
    
    ![MyDomain-BP-Redelegate-1-3-2](../../media/19307893-2f73-4e4d-9221-a5870e09ab48.png)
  
3. <span data-ttu-id="0446b-163">레코드의 상자에 다음 표의 이름 서버 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-163">In the boxes for the records, type or copy and paste the nameserver values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="0446b-164">**이름 서버 1**</span><span class="sxs-lookup"><span data-stu-id="0446b-164">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="0446b-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="0446b-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="0446b-166">**이름 서버 2**</span><span class="sxs-lookup"><span data-stu-id="0446b-166">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="0446b-167">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="0446b-167">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="0446b-168">**이름 서버 3**</span><span class="sxs-lookup"><span data-stu-id="0446b-168">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="0446b-169">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="0446b-169">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="0446b-170">**이름 서버 4**</span><span class="sxs-lookup"><span data-stu-id="0446b-170">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="0446b-171">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="0446b-171">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![MyDomain-BP-Redelegate-1-4](../../media/7427e99c-49c7-4a2e-a5bf-66fc46900cd1.png)
  
4. <span data-ttu-id="0446b-173">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-173">Select **Save**.</span></span>
    
    ![MyDomain-BP-Redelegate-1-5](../../media/48473816-b881-47f0-9344-74622efa3bf8.png)
  
> [!NOTE]
> <span data-ttu-id="0446b-175">이름 서버 레코드 업데이트가 인터넷의 DNS 시스템 전체에 업데이트되기까지 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-175">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="0446b-176">그러면 Microsoft 전자 메일 및 기타 서비스가 모두 도메인에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0446b-176">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
