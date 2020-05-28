---
title: Bluehost을 사용 하 여 Microsoft를 설정 하도록 이름 서버 변경
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
ms.assetid: 7712b6af-329c-43a0-af7b-c4e4c1befb0e
description: 'Bluehost에서 DNS 레코드를 관리 하도록 Microsoft를 설정 하는 방법을 알아봅니다. '
ms.openlocfilehash: 56ebeab025984f0ecfefa579c8060578a2299073
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400668"
---
# <a name="change-nameservers-to-set-up-microsoft-with-bluehost"></a><span data-ttu-id="7a2bc-103">Bluehost을 사용 하 여 Microsoft를 설정 하도록 이름 서버 변경</span><span class="sxs-lookup"><span data-stu-id="7a2bc-103">Change nameservers to set up Microsoft with Bluehost</span></span>

 <span data-ttu-id="7a2bc-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="7a2bc-105">Microsoft에서 DNS 레코드를 관리 하도록 하려면 다음 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="7a2bc-106">원하는 경우 [Bluehost에서 모든 DNS 레코드를 관리할](create-dns-records-at-bluehost.md)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-106">(If you prefer, you can [manage all your DNS records at Bluehost](create-dns-records-at-bluehost.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="7a2bc-107">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="7a2bc-107">Add a TXT record for verification</span></span>

<span data-ttu-id="7a2bc-p102">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7a2bc-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="7a2bc-112">시작하려면 [이 링크](https://my.bluehost.com/cgi/dm)를 사용하여 Bluehost의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-112">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="7a2bc-113">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-113">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="7a2bc-114">**domains(도메인)** 페이지의 **domain(도메인)** 영역에서 변경 중인 도메인의 행을 찾아 해당 도메인의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-114">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="7a2bc-115">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="7a2bc-115">(You may have to scroll down.)</span></span> 
    
3. <span data-ttu-id="7a2bc-116">**Domain_name** 영역의 **dns 영역 편집기** 행에서 **dns 레코드 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-116">In the **domain_name** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="7a2bc-117">On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-117">On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="7a2bc-118">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="7a2bc-118">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7a2bc-119">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="7a2bc-119">**Host Record**</span></span> <br/> |<span data-ttu-id="7a2bc-120">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7a2bc-120">**TTL**</span></span> <br/> |<span data-ttu-id="7a2bc-121">**종류**</span><span class="sxs-lookup"><span data-stu-id="7a2bc-121">**Type**</span></span> <br/> |<span data-ttu-id="7a2bc-122">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="7a2bc-122">**TXT Value**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="7a2bc-123">14400</span><span class="sxs-lookup"><span data-stu-id="7a2bc-123">14400</span></span>  <br/> |<span data-ttu-id="7a2bc-124">TXT</span><span class="sxs-lookup"><span data-stu-id="7a2bc-124">TXT</span></span>  <br/> |<span data-ttu-id="7a2bc-125">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="7a2bc-125">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="7a2bc-126">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-126">**Note:** This is an example.</span></span> <span data-ttu-id="7a2bc-127">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-127">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="7a2bc-128">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="7a2bc-128">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
5. <span data-ttu-id="7a2bc-129">**레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-129">Select **add record**.</span></span>
    
6. <span data-ttu-id="7a2bc-130">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-130">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="7a2bc-131">도메인 등록 기관 사이트에서 레코드를 추가 했으므로 이제 Microsoft로 이동 하 여 레코드 검색을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-131">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="7a2bc-132">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-132">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="7a2bc-133">Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-133">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="7a2bc-134">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-134">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="7a2bc-135">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-135">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="7a2bc-136">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-136">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7a2bc-137">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-137">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="7a2bc-138">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-138">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="7a2bc-139">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-139">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="7a2bc-140">도메인의 NS(이름 서버) 레코드 변경</span><span class="sxs-lookup"><span data-stu-id="7a2bc-140">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="7a2bc-141">Microsoft에서 도메인 설정을 완료 하려면 도메인 등록 기관에서 도메인의 NS 레코드를 기본 및 보조 이름 서버를 가리키도록 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-141">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the  primary and secondary name servers.</span></span> <span data-ttu-id="7a2bc-142">이렇게 하면 Microsoft에서 도메인의 DNS 레코드를 업데이트 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-142">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="7a2bc-143">전자 메일, 비즈니스용 Skype Online, 공개 웹 사이트가 사용자의 도메인을 사용하도록 모든 레코드가 자동으로 추가되고 모든 설정이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-143">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="7a2bc-144">Microsoft 이름 서버를 가리키도록 도메인의 NS 레코드를 변경 하면 현재 도메인에 연결 된 모든 서비스가 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-144">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="7a2bc-145">예를 들어 도메인으로 전송 되는 모든 전자 메일 (rob@ *your_domain* )이 변경 된 후 Microsoft로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-145">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="7a2bc-146">다음 절차에서는 목록에서 원치 않는 이름 서버를 삭제 하는 방법 및 올바른 이름 서버가 나열 되어 있지 않은 경우 추가 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-146">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="7a2bc-147">>이 섹션의 단계를 완료 한 후에는 > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com와 같은 4 가지 이름 서버를 나열 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-147">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="7a2bc-148">시작하려면 [이 링크](https://my.bluehost.com/cgi/dm)를 사용하여 Bluehost의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-148">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="7a2bc-149">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-149">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="7a2bc-150">**도메인** 페이지의 **domain_name** 영역에서 도메인에 대 한 확인란을 선택한 다음 **이름 서버**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-150">On the **domains** page, in the **domain_name** area, select the checkbox for your domain, and then select **name servers**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-1](../../media/8f384386-197c-4272-9675-82037922dac4.png)
  
3. <span data-ttu-id="7a2bc-152">**Domain_name** 영역에서 **사용자 지정 이름 서버 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-152">In the **domain_name** area, select **Use Custom Nameservers**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-2](../../media/9fb47d21-c4ce-4eee-af90-c9569870a329.png)
  
4. <span data-ttu-id="7a2bc-154">현재 표시된 페이지에 이름 서버가 이미 나열되어 있는지 여부에 따라 다음 두 가지 절차 중 하나를 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-154">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="7a2bc-155">이미 나열된 이름 서버가 **없으면**[나열된 이름 서버가 없으면](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="7a2bc-155">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="7a2bc-156">이미 나열된 이름 서버가 **있으면**[이름 서버가 나열되어 있는 경우](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="7a2bc-156">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="7a2bc-157">나열된 이름 서버가 없으면</span><span class="sxs-lookup"><span data-stu-id="7a2bc-157">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="7a2bc-158">**사용자 지정 이름 서버 사용** 구역에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-158">In the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="7a2bc-159">**첫 번째 빈 행**</span><span class="sxs-lookup"><span data-stu-id="7a2bc-159">**First empty row**</span></span> <br/> |<span data-ttu-id="7a2bc-160">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="7a2bc-160">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="7a2bc-161">**두 번째 빈 행**</span><span class="sxs-lookup"><span data-stu-id="7a2bc-161">**Second empty row**</span></span> <br/> |<span data-ttu-id="7a2bc-162">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="7a2bc-162">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-Redelegate-1-3-1](../../media/07b13d6d-a34e-45b5-afd5-48ebd4c1344f.png)
  
2. <span data-ttu-id="7a2bc-164">**행 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-164">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
3. <span data-ttu-id="7a2bc-166">계속 **Use Custom Nameservers**(사용자 지정 이름 서버 사용) 구역에서 다음 표에 나온 첫 번째 행의 값을 새 빈 행에 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-166">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="7a2bc-167">**세 번째 빈 행**</span><span class="sxs-lookup"><span data-stu-id="7a2bc-167">**Third empty row**</span></span> <br/> |<span data-ttu-id="7a2bc-168">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="7a2bc-168">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="7a2bc-169">**네 번째 빈 행**</span><span class="sxs-lookup"><span data-stu-id="7a2bc-169">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="7a2bc-170">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="7a2bc-170">ns4.bdm.microsoftonline.com</span></span>  <br/> |
  
4. <span data-ttu-id="7a2bc-171">네 번째 이름 서버 레코드를 추가 하려면 **행 추가** 를 다시 선택 하 고 위의 표에 있는 마지막 행의 값을 사용 하 여 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-171">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
5. <span data-ttu-id="7a2bc-172">**이름 서버 설정 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-172">Select **save nameserver settings**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-4](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="7a2bc-174">이름 서버 레코드 업데이트가 인터넷의 DNS 시스템 전체에 업데이트되기까지 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-174">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="7a2bc-175">그러면 Microsoft 전자 메일 및 기타 서비스가 모두 도메인에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-175">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="7a2bc-176">이름 서버가 나열되어 있는 경우</span><span class="sxs-lookup"><span data-stu-id="7a2bc-176">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="7a2bc-177">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-177">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="7a2bc-178">(즉, **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**또는 **ns4.bdm.microsoftonline.com**로 이름이 지정 *되지* 않은 현재 이름 서버 삭제 합니다.)</span><span class="sxs-lookup"><span data-stu-id="7a2bc-178">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="7a2bc-179">다른 이름 서버가 나열되어 있으면 하나씩 선택한 후 키보드의 **Delete** 키를 눌러 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-179">If there are any other name servers listed, delete each of them by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Bluehost-BP-Redelegate-1-5](../../media/d1051c43-f8ff-46d7-af26-3975d3f0f621.png)
  
2. <span data-ttu-id="7a2bc-181">계속 **사용자 지정 이름 서버 사용** 구역에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-181">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="7a2bc-182">**첫 번째 빈 행**</span><span class="sxs-lookup"><span data-stu-id="7a2bc-182">**First empty row**</span></span> <br/> |<span data-ttu-id="7a2bc-183">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="7a2bc-183">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="7a2bc-184">**두 번째 빈 행**</span><span class="sxs-lookup"><span data-stu-id="7a2bc-184">**Second empty row**</span></span> <br/> |<span data-ttu-id="7a2bc-185">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="7a2bc-185">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-Redelegate-1-3](../../media/1523debf-5eb0-4765-8e05-bcd56e375c20.png)
  
3. <span data-ttu-id="7a2bc-187">**행 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-187">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
4. <span data-ttu-id="7a2bc-189">계속 **Use Custom Nameservers**(사용자 지정 이름 서버 사용) 구역에서 다음 표에 나온 첫 번째 행의 값을 새 빈 행에 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-189">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="7a2bc-190">**세 번째 빈 행**</span><span class="sxs-lookup"><span data-stu-id="7a2bc-190">**Third empty row**</span></span> <br/> |<span data-ttu-id="7a2bc-191">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="7a2bc-191">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="7a2bc-192">**네 번째 빈 행**</span><span class="sxs-lookup"><span data-stu-id="7a2bc-192">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="7a2bc-193">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="7a2bc-193">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-Redelegate-1-3-3](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
5. <span data-ttu-id="7a2bc-195">네 번째 이름 서버 레코드를 추가 하려면 **행 추가** 를 다시 선택 하 고 위의 표에 있는 마지막 행의 값을 사용 하 여 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-195">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
6. <span data-ttu-id="7a2bc-196">**이름 서버 설정 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-196">Select **save nameserver settings**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-4](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="7a2bc-198">이름 서버 레코드 업데이트가 인터넷의 DNS 시스템 전체에 업데이트되기까지 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-198">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="7a2bc-199">그러면 Microsoft 전자 메일 및 기타 서비스가 모두 도메인에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a2bc-199">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
