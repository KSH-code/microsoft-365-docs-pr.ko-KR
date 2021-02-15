---
title: 1 IONOS가 1인 경우 이름&변경
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
ms.assetid: 31efc571-c8b9-46fb-b42d-203c2fb25289
description: 21Vianet에서 운영하는 Office 365를 설정하여 DNS 레코드를 관리하는 방법을 알아보고, DNS 호스팅 공급자로는 1&인터넷이 있습니다.
ms.openlocfilehash: b363718c7d1d1845117f44317ae9e6b24e9a2e28
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658035"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-11-ionos"></a><span data-ttu-id="a624b-103">1 IONOS가 1인 Microsoft 365를 설정하기 위해&변경</span><span class="sxs-lookup"><span data-stu-id="a624b-103">Change nameservers to set up Microsoft 365 with 1&1 IONOS</span></span>

 <span data-ttu-id="a624b-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="a624b-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a624b-105">Microsoft 365에서 Microsoft 365 DNS 레코드를 관리하게 하려는 경우 다음 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-105">Follow these instructions if you want Microsoft 365 to manage your Microsoft 365 DNS records for you.</span></span> <span data-ttu-id="a624b-106">원하는 경우 모든 [Microsoft 365 DNS 레코드를 1 1 IONOS에서](create-dns-records-at-1-1-internet.md)&수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-106">(If you prefer, you can [manage all your Microsoft 365 DNS records at 1&1 IONOS](create-dns-records-at-1-1-internet.md).)</span></span> 
  

    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a624b-107">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="a624b-107">Add a TXT record for verification</span></span>


<span data-ttu-id="a624b-p102">Microsoft 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft 365에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-p102">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a624b-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="a624b-112">아래 단계를 따르거나 [비디오를 시청하세요(0:42에 시작)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).</span><span class="sxs-lookup"><span data-stu-id="a624b-112">Follow the steps below or [watch the video (start at 0:42)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).</span></span>
  
1. <span data-ttu-id="a624b-113">To get started, go to your domains page at 1&1 IONOS via [this link.](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F)</span><span class="sxs-lookup"><span data-stu-id="a624b-113">To get started, go to your domains page at 1&1 IONOS via [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span></span> <span data-ttu-id="a624b-114">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="a624b-114">You'll be prompted to log in.</span></span> 
    
2. <span data-ttu-id="a624b-115">MY **DOMAINS에서** 도메인 **관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a624b-115">Under **MY DOMAINS**, select **Manage domains**.</span></span>
    
3. <span data-ttu-id="a624b-116">On the **Domain Center** page, find the domain that you want to update; 그런 다음 해당 **도메인에** 대한 **패널(v)** 컨트롤을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-116">On the **Domain Center** page, find the domain that you want to update; then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="a624b-117">도메인 설정 **영역에서** DNS 설정 **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a624b-117">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="a624b-118">**TXT 및 SRV 레코드** 섹션에서 레코드 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a624b-118">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
    <span data-ttu-id="a624b-119">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="a624b-119">(You may have to scroll down.)</span></span> 
    
6. <span data-ttu-id="a624b-120">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="a624b-120">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="a624b-121">**종류**</span><span class="sxs-lookup"><span data-stu-id="a624b-121">**Type**</span></span> <br/> |<span data-ttu-id="a624b-122">**Prefix(접두사)**</span><span class="sxs-lookup"><span data-stu-id="a624b-122">**Prefix**</span></span> <br/> |<span data-ttu-id="a624b-123">**Name Value(이름 값)**</span><span class="sxs-lookup"><span data-stu-id="a624b-123">**Name Value**</span></span> <br/> |
|<span data-ttu-id="a624b-124">TXT</span><span class="sxs-lookup"><span data-stu-id="a624b-124">TXT</span></span>  <br/> |<span data-ttu-id="a624b-125">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="a624b-125">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="a624b-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a624b-126">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="a624b-127">**참고**: 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-127">**Note**: This is an example.</span></span> <span data-ttu-id="a624b-128">여기에는 Microsoft 365의 표에 있는 특정 **주소를 지정할 대상 또는 지점** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-128">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span> [<span data-ttu-id="a624b-129">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="a624b-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
7. <span data-ttu-id="a624b-130">**저장을** 선택한 다음 다시 **저장을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-130">Select **Save**, and then **Save** again.</span></span> 
    
8. <span data-ttu-id="a624b-131">DNS 설정 **편집** 대화 상자에서 **예를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a624b-131">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
9. <span data-ttu-id="a624b-132">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a624b-133">이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft 365로 돌아가서 Microsoft 365에 레코드를 찾을 것을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="a624b-134">Microsoft 365에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-134">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a624b-135">I관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인</a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="a624b-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="a624b-136">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="a624b-137">**설정** 페이지에서 **설정 시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="a624b-138">**도메인 확인** 페이지에서 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a624b-139">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="a624b-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="a624b-140">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="a624b-141">DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [Microsoft 365에서](../get-help-with-domains/find-and-fix-issues.md)도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="a624b-142">도메인의 NS(이름 서버) 레코드 변경</span><span class="sxs-lookup"><span data-stu-id="a624b-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="a624b-143">Microsoft 365를 사용하여 도메인 설정을 완료하려면 도메인 등록 기관에서 Microsoft 365 기본 및 보조 이름 서버를 지점으로 도메인의 NS 레코드를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-143">To complete setting up your domain with Microsoft 365, you change your domain's NS records at your domain registrar to point to the Microsoft 365 primary and secondary name servers.</span></span> <span data-ttu-id="a624b-144">이렇게 하면 Microsoft 365가 도메인의 DNS 레코드를 자동으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-144">This sets up Microsoft 365 to update the domain's DNS records for you.</span></span> <span data-ttu-id="a624b-145">전자 메일, 비즈니스용 Skype Online, 공개 웹 사이트가 사용자의 도메인을 사용하도록 모든 레코드가 자동으로 추가되고 모든 설정이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-145">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="a624b-146">Microsoft 365 이름 서버를 지점으로 도메인의 NS 레코드를 변경하면 현재 도메인과 연결된 모든 서비스가 영향을 받는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-146">When you change your domain's NS records to point to the Microsoft 365 name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="a624b-147">예를 들어 도메인으로 전송된 모든 전자 메일(예: rob@ *your_domain*  .com)은 이 변경을 한 후 Microsoft 365로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-147">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft 365 after you make this change.</span></span> 
  
<span data-ttu-id="a624b-148">Microsoft 365에서 도메인을 설정할 수 있도록 NS 레코드를 변경할 준비가 되신가요?</span><span class="sxs-lookup"><span data-stu-id="a624b-148">Ready to change your NS records so Microsoft 365 can set up your domain?</span></span> <span data-ttu-id="a624b-149">아래 단계를 따르거나 [비디오를 시청하세요(2:47에 시작).](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3)</span><span class="sxs-lookup"><span data-stu-id="a624b-149">Follow the steps below or [watch the video (start at 2:47)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="a624b-150">다음 절차에서는 원치 않는 다른 이름 서스터를 목록에서 삭제하는 방법과 올바른 이름 서비스(아직 나열되지 않은 경우)를 추가하는 방법을 보여 합니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-150">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="a624b-151">> 이 섹션의 단계를 완료하면 다음 네 가지 이름만 나열됩니다. > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a624b-151">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="a624b-152">To get started, go to your domains page at 1&1 IONOS by using [this link.](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F)</span><span class="sxs-lookup"><span data-stu-id="a624b-152">To get started, go to your domains page at 1&1 IONOS by using [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span></span> <span data-ttu-id="a624b-153">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="a624b-153">You'll be prompted to log in.</span></span> 
    
2. <span data-ttu-id="a624b-154">MY **DOMAINS에서** 도메인 **관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a624b-154">Under **MY DOMAINS**, select **Manage domains**.</span></span>
    
3. <span data-ttu-id="a624b-155">도메인 센터 **페이지에서** 업데이트할 도메인을 찾은 다음 해당 도메인에 대한 **패널(v)** 컨트롤을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="a624b-155">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="a624b-156">도메인 설정 **영역에서** DNS 설정 **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a624b-156">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="a624b-157">**이름 서버 설정** 구역에서 **다른 이름 서버** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-157">In the **Name Server Settings** section, select **Other name servers**.</span></span>
    
    <span data-ttu-id="a624b-158">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="a624b-158">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="a624b-159">현재 표시된 페이지에 이름 서버가 이미 나열되어 있는지 여부에 따라 다음 두 가지 절차 중 하나를 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="a624b-160">이미 나열된 이름 서버가 **없으면**[나열된 이름 서버가 없으면](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="a624b-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="a624b-161">이미 나열된 이름 서버가 **있으면**[이름 서버가 나열되어 있는 경우](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="a624b-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="a624b-162">나열된 이름 서버가 없으면</span><span class="sxs-lookup"><span data-stu-id="a624b-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="a624b-163">**이름 서버 1** 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-163">In the **Name server 1** box, type or copy and paste the value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="a624b-164">**이름 서버 1**</span><span class="sxs-lookup"><span data-stu-id="a624b-164">**Name server 1**</span></span> <br/> |<span data-ttu-id="a624b-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a624b-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![이름 서버 1 상자에 값 입력](../../media/34509935-461f-427f-9796-c3cf840bd9be.png)
  
2. <span data-ttu-id="a624b-167">**다른 이름 서버** 드롭다운 목록에서 **내 보조 이름 서버** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-167">In the **Additional name servers** drop-down list, choose **My secondary name servers**.</span></span>
    
    ![Choosing My secondary name servers in the list](../../media/7eb14856-86da-45c2-910c-c72312250a18.png)
  
3. <span data-ttu-id="a624b-169">**이름 서버 2, 3, 4** 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-169">In the **Name server 2, 3, and 4** boxes, type or copy and paste the value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="a624b-170">**이름 서버 2**</span><span class="sxs-lookup"><span data-stu-id="a624b-170">**Name server 2**</span></span> <br/> |<span data-ttu-id="a624b-171">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a624b-171">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="a624b-172">**이름 서버 3**</span><span class="sxs-lookup"><span data-stu-id="a624b-172">**Name server 3**</span></span> <br/> |<span data-ttu-id="a624b-173">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a624b-173">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="a624b-174">**이름 서버 4**</span><span class="sxs-lookup"><span data-stu-id="a624b-174">**Name server 4**</span></span> <br/> |<span data-ttu-id="a624b-175">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a624b-175">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
![이름 서버 값 입력](../../media/0f15880c-88b6-4133-8f31-62f0d98ee63f.png)
  
4. <span data-ttu-id="a624b-177">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-177">Select **Save**.</span></span>
    
    ![이름 서버 설정에서 저장 선택 페이지](../../media/864f7927-7127-4784-b8d2-dadfea2f9dc8.png)
  
5. <span data-ttu-id="a624b-179">DNS 설정 **편집** 대화 상자에서 **예를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a624b-179">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
    ![DNS 설정 편집 대화 상자에서 저장 선택](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> <span data-ttu-id="a624b-181">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="a624b-181">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="a624b-182">그런 다음 Microsoft 전자 메일 및 기타 서비스가 모두 도메인에서 작동하게 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-182">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="a624b-183">이름 서버가 나열되어 있는 경우</span><span class="sxs-lookup"><span data-stu-id="a624b-183">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="a624b-p113">네 개의  *올바른*  이름 서버 외에 기존 이름 서버가 있는 경우에  *만*  다음 단계를 따릅니다(즉, 이름이 *ns1.bdm.microsoftonline.com*, *ns2.bdm.microsoftonline.com*, **ns3.bdm.microsoftonline.com** 또는 **ns4.bdm.microsoftonline.com** 이  **아닌**  현재 모든 이름 서버  **만**  삭제).</span><span class="sxs-lookup"><span data-stu-id="a624b-p113">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="a624b-186">**이름 서버** 상자에 이미 이름 서버가 나열되어 있으면 하나씩 선택한 후 키보드의 **Delete** 키를 눌러 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-186">If there are already nameservers listed in the **Name server** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting name servers](../../media/af0a68cc-b058-4925-b3b1-52dfded003c1.png)
  
2. <span data-ttu-id="a624b-188">**이름 서버 1, 2, 3, 4** 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-188">In the **Name server 1, 2, 3, and 4** boxes, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="a624b-189">**이름 서버 1**</span><span class="sxs-lookup"><span data-stu-id="a624b-189">**Name server 1**</span></span> <br/> |<span data-ttu-id="a624b-190">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a624b-190">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="a624b-191">**이름 서버 2**</span><span class="sxs-lookup"><span data-stu-id="a624b-191">**Name server 2**</span></span> <br/> |<span data-ttu-id="a624b-192">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a624b-192">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="a624b-193">**이름 서버 3**</span><span class="sxs-lookup"><span data-stu-id="a624b-193">**Name server 3**</span></span> <br/> |<span data-ttu-id="a624b-194">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a624b-194">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="a624b-195">**이름 서버 4**</span><span class="sxs-lookup"><span data-stu-id="a624b-195">**Name server 4**</span></span> <br/> |<span data-ttu-id="a624b-196">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a624b-196">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![이름 서버 값 입력](../../media/52826bd1-0596-4103-a728-d5d28b9610d2.png)
  
3. <span data-ttu-id="a624b-198">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-198">Select **Save**.</span></span>
    
    ![이름 서버 설정에서 저장 선택 페이지](../../media/cd10e4fb-b7fa-480f-855b-a443f2705cf2.png)
  
4. <span data-ttu-id="a624b-200">DNS 설정 **편집** 대화 상자에서 **예를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a624b-200">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
    ![DNS 설정 편집 대화 상자에서 저장 선택](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> <span data-ttu-id="a624b-202">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="a624b-202">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="a624b-203">그런 다음 Microsoft 전자 메일 및 기타 서비스가 모두 도메인에서 작동하게 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a624b-203">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  


