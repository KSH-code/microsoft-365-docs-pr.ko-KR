---
title: MyDomain에서 이름 서퍼를 변경하여 Microsoft 설정
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
ms.assetid: c5f6140a-4a12-401b-9bbd-7dfb0d6b0ba3
description: MyDomain에서 사용자 지정 도메인의 DNS 레코드를 관리하기 위해 Microsoft를 설정하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: fbfa3c495f54a9890be6d9c9e31a7878b21f12fe
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658419"
---
# <a name="change-nameservers-to-set-up-microsoft-with-mydomain"></a><span data-ttu-id="6e11e-103">MyDomain에서 이름 서퍼를 변경하여 Microsoft 설정</span><span class="sxs-lookup"><span data-stu-id="6e11e-103">Change nameservers to set up Microsoft with MyDomain</span></span>

 <span data-ttu-id="6e11e-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="6e11e-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="6e11e-105">Microsoft에서 DNS 레코드를 관리하게 하려는 경우 다음 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="6e11e-106">원하는 경우 [MyDomain에서 모든 Microsoft DNS 레코드를 관리할 수 있습니다.](create-dns-records-at-mydomain.md)</span><span class="sxs-lookup"><span data-stu-id="6e11e-106">(If you prefer, you can [manage all your Microsoft DNS records at MyDomain](create-dns-records-at-mydomain.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="6e11e-107">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="6e11e-107">Add a TXT record for verification</span></span>

<span data-ttu-id="6e11e-p102">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6e11e-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="6e11e-p104">시작하려면 [이 링크](https://www.mydomain.com/controlpanel)를 사용하여 MyDomain의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-p104">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="6e11e-114">**내 즐겨 찾기** 섹션에서 **도메인 센터** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-114">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="6e11e-115">**도메인** 에서 편집할 도메인 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-115">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="6e11e-116">**개요** 행에서 **DNS** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-116">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="6e11e-117">**수정** 드롭다운 목록에서 **TXT/SPF 레코드** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-117">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="6e11e-118">
            \*\*콘텐츠\*\* 아래의 새 레코드에 대한 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-118">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
||
|:-----|
|<span data-ttu-id="6e11e-119">**콘텐츠**</span><span class="sxs-lookup"><span data-stu-id="6e11e-119">**Content**</span></span> <br/> |
|<span data-ttu-id="6e11e-120">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="6e11e-120">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="6e11e-121">**참고**: 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-121">**Note**: This is an example.</span></span> <span data-ttu-id="6e11e-122">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-122">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="6e11e-123">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="6e11e-123">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="6e11e-124">**추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-124">Select **Add**.</span></span>
    
8. <span data-ttu-id="6e11e-125">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-125">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="6e11e-126">이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft 365로 돌아가서 Microsoft 365에 레코드를 찾을 것을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-126">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="6e11e-127">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-127">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="6e11e-128">Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-128">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="6e11e-129">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-129">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="6e11e-130">**설정** 페이지에서 **설정 시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-130">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="6e11e-131">**도메인 확인** 페이지에서 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-131">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6e11e-132">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="6e11e-132">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="6e11e-133">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-133">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="6e11e-134">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6e11e-134">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="6e11e-135">도메인의 NS(이름 서버) 레코드 변경</span><span class="sxs-lookup"><span data-stu-id="6e11e-135">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="6e11e-136">Microsoft에서 도메인 설정을 완료하려면 도메인 등록 기관에서 Microsoft 기본 및 보조 이름 서버를 설정하기 위해 도메인의 NS 레코드를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-136">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="6e11e-137">이렇게 하면 도메인의 DNS 레코드가 자동으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-137">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="6e11e-138">전자 메일, 비즈니스용 Skype Online, 공개 웹 사이트가 사용자의 도메인을 사용하도록 모든 레코드가 자동으로 추가되고 모든 설정이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-138">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="6e11e-139">Microsoft 이름 서버를 설정하기 위해 도메인의 NS 레코드를 변경하면 현재 도메인과 연결된 모든 서비스가 영향을 받는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-139">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="6e11e-140">예를 들어 도메인으로 전송된 모든 전자 메일(예: rob@ *your_domain.*</span><span class="sxs-lookup"><span data-stu-id="6e11e-140">For example, all email sent to your domain (like rob@ *your_domain.*</span></span> <span data-ttu-id="6e11e-141">com) 이 변경을 한 후 Microsoft에 다가오기 시작할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-141">com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="6e11e-142">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span><span class="sxs-lookup"><span data-stu-id="6e11e-142">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span></span> <br/> <span data-ttu-id="6e11e-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span><span class="sxs-lookup"><span data-stu-id="6e11e-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span>
  
1. <span data-ttu-id="6e11e-p110">시작하려면 [이 링크](https://www.mydomain.com/controlpanel)를 사용하여 MyDomain의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="6e11e-146">**내 즐겨 찾기** 섹션에서 **도메인 센터** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-146">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="6e11e-147">**도메인** 에서 편집할 도메인 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-147">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="6e11e-148">개요 **행에서** **Nameservers를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6e11e-148">In the **Overview** row, select **Nameservers**.</span></span>
    
    ![MyDomain-BP-Redelegate-1-1](../../media/49e91235-44b5-46d6-a82e-8f11329db3d6.png)
  
5. <span data-ttu-id="6e11e-150">**Update Name Servers(이름 서버 업데이트)** 구역에서 **Use different name servers(다른 이름 서버 사용)** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-150">In the **Update Name Servers** section, select **Use different name servers**.</span></span>
    
    ![MyDomain-BP-Redelegate-1-2-1](../../media/f869fb26-54dc-4b66-8378-a78a79b582bd.png)
  
6. <span data-ttu-id="6e11e-152">현재 표시된 페이지에 이름Servers가 이미 나열되어 있는지 여부에 따라 다음 두 절차 중 하나를 계속 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-152">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-the-correct-nameservers-are-already-listed"></a><span data-ttu-id="6e11e-153">올바른 이름 서버가 이미 나열되어 있으면</span><span class="sxs-lookup"><span data-stu-id="6e11e-153">If the correct nameservers ARE already listed</span></span>

- <span data-ttu-id="6e11e-154">올바른 이름 서버가 이미 나열되어 있으면 이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-154">If the correct nameservers are already listed, you can skip this step.</span></span>
    
    ![MyDomain-BP-Redelegate-1-2-2](../../media/601f6a46-15bd-4a92-b792-ac628ff86628.png)
  
### <a name="if-the-correct-nameservers-are-not-already-listed"></a><span data-ttu-id="6e11e-156">올바른 이름 서버가 나열되어 있지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="6e11e-156">If the correct nameservers are NOT already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="6e11e-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="6e11e-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="6e11e-158">즉, 이름이 **ns1.bdm.microsoftonline.com,** ns2.bdm.microsoftonline.com, ns3.bdm.microsoftonline.com  또는 ns4.bdm.microsoftonline.com **이름** 없는 모든 현재 이름 ns4.bdm.microsoftonline.com 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-158">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="6e11e-159">**Nameserver:**(이름 서버:) 필드에서 각 항목을 선택한 다음 키보드에서 **Delete** 키를 눌러 기존 이름 서버를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-159">Delete the existing nameservers by selecting each entry in the **Nameserver:** field, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![MyDomain-BP-Redelegate-1-3-1](../../media/5024cd27-a2b1-42a2-99e4-5ceb5e6eddb9.png)
  
2. <span data-ttu-id="6e11e-161">두 **번 더 추가를** 선택하여 두 개의 새 이름 서비스 행을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-161">Select **Add More** twice to add two new Nameserver rows.</span></span> 
    
    ![MyDomain-BP-Redelegate-1-3-2](../../media/19307893-2f73-4e4d-9221-a5870e09ab48.png)
  
3. <span data-ttu-id="6e11e-163">레코드의 상자에 다음 표의 이름 서버 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-163">In the boxes for the records, type or copy and paste the nameserver values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="6e11e-164">**이름 서버 1**</span><span class="sxs-lookup"><span data-stu-id="6e11e-164">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="6e11e-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6e11e-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="6e11e-166">**이름 서버 2**</span><span class="sxs-lookup"><span data-stu-id="6e11e-166">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="6e11e-167">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6e11e-167">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="6e11e-168">**이름 서버 3**</span><span class="sxs-lookup"><span data-stu-id="6e11e-168">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="6e11e-169">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6e11e-169">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="6e11e-170">**이름 서버 4**</span><span class="sxs-lookup"><span data-stu-id="6e11e-170">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="6e11e-171">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6e11e-171">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![MyDomain-BP-Redelegate-1-4](../../media/7427e99c-49c7-4a2e-a5bf-66fc46900cd1.png)
  
4. <span data-ttu-id="6e11e-173">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-173">Select **Save**.</span></span>
    
    ![MyDomain-BP-Redelegate-1-5](../../media/48473816-b881-47f0-9344-74622efa3bf8.png)
  
> [!NOTE]
> <span data-ttu-id="6e11e-175">이름 서버 레코드 업데이트가 인터넷의 DNS 시스템 전체에 업데이트되기까지 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-175">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="6e11e-176">그런 다음 Microsoft 전자 메일 및 기타 서비스가 모두 도메인에서 작동하게 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e11e-176">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
