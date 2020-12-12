---
title: 네트워크 솔루션에서 이름 서비스를 변경하여 Microsoft 설정
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
ms.assetid: d4ba60f3-4e1c-4180-99bd-250b8955be2a
description: 'Microsoft에서 DNS 레코드를 관리하게 하려는 경우 네트워크 솔루션으로 Microsoft 사용자 지정 도메인을 설정하는 방법을 알아보십시오. '
ms.openlocfilehash: 04817ca24b13b4c138986df3875b6d397100fffd
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658431"
---
# <a name="change-nameservers-to-set-up-microsoft-with-network-solutions"></a><span data-ttu-id="78c84-103">네트워크 솔루션에서 이름 서비스를 변경하여 Microsoft 설정</span><span class="sxs-lookup"><span data-stu-id="78c84-103">Change nameservers to set up Microsoft with Network Solutions</span></span>

 <span data-ttu-id="78c84-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="78c84-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="78c84-105">Microsoft에서 DNS 레코드를 관리하게 하려는 경우 다음 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="78c84-106">원하는 경우 네트워크 솔루션에서 [모든 Microsoft DNS 레코드를 관리할 수 있습니다.](create-dns-records-at-network-solutions.md)</span><span class="sxs-lookup"><span data-stu-id="78c84-106">(If you prefer, you can [manage all your Microsoft DNS records at Network Solutions](create-dns-records-at-network-solutions.md).)</span></span>
  
    
## <a name="add-a-txt-record-at-network-solutions-to-verify-that-you-own-the-domain"></a><span data-ttu-id="78c84-107">Network Solutions에서 TXT 레코드를 추가해 도메인을 소유하고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="78c84-107">Add a TXT record at Network Solutions to verify that you own the domain</span></span>

<span data-ttu-id="78c84-p102">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="78c84-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="78c84-112">아래 단계를 따르거나 [비디오를 시청하세요(0:47에 시작)](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261).</span><span class="sxs-lookup"><span data-stu-id="78c84-112">Follow the steps below or [watch the video (start at 0:47)](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261).</span></span>
  
1. <span data-ttu-id="78c84-p104">시작하려면 [이 링크](https://www.networksolutions.com/manage-it)를 사용하여 Network Solutions의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-p104">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="78c84-115">로그인 **단추를 선택하기** 전에  먼저 로그인 **대상:** 드롭다운 목록에서 내 도메인 이름 관리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-115">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span>
  
    ![Manage My Domain Names(내 도메인 이름 관리)를 선택하고 Network Solutions에 로그인합니다.](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="78c84-117">수정하려는 도메인 이름 옆의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-117">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![도메인에 대한 확인란을 선택합니다.](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="78c84-119">DNS **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="78c84-119">Select **Edit DNS**.</span></span>
    
    ![DNS 편집 선택](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="78c84-121">고급 **DNS 레코드 관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="78c84-121">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="78c84-122">(아래로 스크롤해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="78c84-122">(You may have to scroll down.)</span></span>
    
    ![고급 DNS 레코드 관리 선택](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="78c84-124">아래로 스크롤하여 **텍스트(TXT 레코드)** 구역으로 이동한 다음 **TXT 레코드 편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="78c84-124">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Select Edit TXT Records](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="78c84-126">새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-126">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
|<span data-ttu-id="78c84-127">**Host**</span><span class="sxs-lookup"><span data-stu-id="78c84-127">**Host**</span></span>|<span data-ttu-id="78c84-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="78c84-128">**TTL**</span></span>|<span data-ttu-id="78c84-129">**텍스트**</span><span class="sxs-lookup"><span data-stu-id="78c84-129">**Text**</span></span>|
|:-----|:-----|:-----|
|@  <br/> <span data-ttu-id="78c84-130">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="78c84-130">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="78c84-131">3600</span><span class="sxs-lookup"><span data-stu-id="78c84-131">3600</span></span>  <br/> |<span data-ttu-id="78c84-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="78c84-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="78c84-133">**참고**: 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-133">**Note**: This is an example.</span></span> <span data-ttu-id="78c84-134">여기에는 Microsoft 365의 표에 있는 특정 **주소를 지정할 대상 또는 지점** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-134">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="78c84-135">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="78c84-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)
   
    
   ![새 레코드의 상자에 값을 입력하거나 붙여넣습니다.](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="78c84-137">계속을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="78c84-137">Select **Continue**.</span></span>
    
    ![계속 선택](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="78c84-139">변경 **내용 저장을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="78c84-139">Select **Save Changes**.</span></span>
    
    ![변경 내용 저장 선택](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="78c84-141">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="78c84-142">이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft 365로 돌아가서 Microsoft 365에 레코드를 찾을 것을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-142">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="78c84-143">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-143">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="78c84-144">Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-144">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="78c84-145">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="78c84-146">**설정** 페이지에서 **설정 시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-146">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="78c84-147">**도메인 확인** 페이지에서 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-147">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="78c84-p106">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78c84-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="78c84-151">도메인의 NS(이름 서버) 레코드 변경</span><span class="sxs-lookup"><span data-stu-id="78c84-151">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="78c84-152">Microsoft에서 도메인 설정을 완료하려면 도메인 등록 기관에서 Microsoft 기본 및 보조 이름 서버를 설정하기 위해 도메인의 NS 레코드를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-152">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="78c84-153">이렇게 하면 도메인의 DNS 레코드가 자동으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-153">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="78c84-154">전자 메일, 비즈니스용 Skype Online, 공개 웹 사이트가 사용자의 도메인을 사용하도록 모든 레코드가 자동으로 추가되고 모든 설정이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-154">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="78c84-155">Microsoft 이름 서버를 설정하기 위해 도메인의 NS 레코드를 변경하면 현재 도메인과 연결된 모든 서비스가 영향을 받는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-155">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="78c84-156">예를 들어 도메인으로 전송된 모든 전자 메일(예: rob@ *your_domain*  .com)은 이 변경 후에 Microsoft로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-156">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span>
  
<span data-ttu-id="78c84-157">Microsoft에서 도메인을 설정할 수 있도록 NS 레코드를 변경할 준비가 되나요?</span><span class="sxs-lookup"><span data-stu-id="78c84-157">Ready to change your NS records so Microsoft can set up your domain?</span></span> <span data-ttu-id="78c84-158">아래 단계를 따르거나 [비디오를 시청하세요(2:23에 시작).](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261)</span><span class="sxs-lookup"><span data-stu-id="78c84-158">Follow the steps below or [watch the video (start at 2:23)](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261).</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="78c84-159">이 섹션의 단계를 완료한 후 나열해야 하는 유일한 이름 ns1.bdm.microsoftonline.com, ns2.bdm.microsoftonline.com, ns3.bdm.microsoftonline.com 및 **ns4.bdm.microsoftonline.com.**  </span><span class="sxs-lookup"><span data-stu-id="78c84-159">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**.</span></span> <span data-ttu-id="78c84-160">다음 절차에는 원치 않는 기타 이름 서버를 목록에서 삭제하는 방법과  *올바른*  이름 서버가 목록에 아직 없는 경우 이를 추가하는 방법이 나타나 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-160">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span></span> 
  
1. <span data-ttu-id="78c84-161">시작하려면 [이 링크](https://www.networksolutions.com/manage-it)를 사용하여 Network Solutions의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-161">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="78c84-162">로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-162">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="78c84-163">로그인 **단추를 선택하기** 전에  먼저 로그인 **대상:** 드롭다운 목록에서 내 도메인 이름 관리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-163">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Manage My Domain Names(내 도메인 이름 관리)를 선택하고 Network Solutions에 로그인합니다.](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="78c84-165">수정하려는 도메인 이름 옆의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-165">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![도메인에 대한 확인란을 선택합니다.](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="78c84-167">DNS **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="78c84-167">Select **Edit DNS**.</span></span>
    
    ![DNS 편집 선택](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="78c84-169">DNS **이동을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="78c84-169">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-Redelegate-1-1](../../media/e57a30f3-63d5-4bcb-84c6-c8be21c261a2.png)
  
5. <span data-ttu-id="78c84-171">현재 표시된 페이지에 이름 서버가 이미 나열되어 있는지 여부에 따라 다음 두 가지 절차 중 하나를 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-171">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="78c84-172">이미 나열된 이름 서버가 **없으면**[나열된 이름 서버가 없으면](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="78c84-172">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="78c84-173">이미 나열된 이름 서버가 **있으면**[이름 서버가 나열되어 있는 경우](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="78c84-173">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="78c84-174">나열된 이름 서버가 없으면</span><span class="sxs-lookup"><span data-stu-id="78c84-174">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="78c84-175">도메인 **페이지의** 도메인 **이름** 서버 지정 섹션에서 이름 서버 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="78c84-175">On the **Domains** page, in the **Specify Domain Name Servers** section, select **Add More Name Servers**.</span></span>
    
    ![NetworkSolutionsBP-Redelegate-1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
2. <span data-ttu-id="78c84-177">**도메인 이름** 페이지에서 다음 표의 이름 서버 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-177">On the **Domain Names** page, type or copy and paste the nameserver values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="78c84-178">**이름 서버 1**</span><span class="sxs-lookup"><span data-stu-id="78c84-178">**Name Server 1**</span></span> <br/> |<span data-ttu-id="78c84-179">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="78c84-179">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="78c84-180">**이름 서버 2**</span><span class="sxs-lookup"><span data-stu-id="78c84-180">**Name Server 2**</span></span> <br/> |<span data-ttu-id="78c84-181">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="78c84-181">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="78c84-182">**이름 서버 2**</span><span class="sxs-lookup"><span data-stu-id="78c84-182">**Name Server 2**</span></span> <br/> |<span data-ttu-id="78c84-183">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="78c84-183">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="78c84-184">**이름 서버 2**</span><span class="sxs-lookup"><span data-stu-id="78c84-184">**Name Server 2**</span></span> <br/> |<span data-ttu-id="78c84-185">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="78c84-185">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    
![NetworkSolutionsBP-Redelegate-1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
3. <span data-ttu-id="78c84-187">DNS **이동을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="78c84-187">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-Redelegate-1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
4. <span data-ttu-id="78c84-189">변경 **내용 저장을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="78c84-189">Select **Save Changes**.</span></span>
    
    ![NetworkSolutionsBP-Redelegate-1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> <span data-ttu-id="78c84-191">이름 서버 레코드 업데이트가 인터넷의 DNS 시스템 전체에 업데이트되기까지 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-191">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="78c84-192">그런 다음 Microsoft 전자 메일 및 기타 서비스가 모두 도메인에서 작동하게 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-192">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="78c84-193">이름 서버가 나열되어 있는 경우</span><span class="sxs-lookup"><span data-stu-id="78c84-193">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="78c84-p113">네 개의  *올바른*  이름 서버 외에 기존 이름 서버가 있는 경우에  *만*  다음 단계를 따릅니다(즉, 이름이 *ns1.bdm.microsoftonline.com*, *ns2.bdm.microsoftonline.com*, **ns3.bdm.microsoftonline.com** 또는 **ns4.bdm.microsoftonline.com** 이  **아닌**  현재 모든 이름 서버  **만**  삭제).</span><span class="sxs-lookup"><span data-stu-id="78c84-p113">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span>
  
1. <span data-ttu-id="78c84-196">다른 이름 서버가 나열되어 있으면 하나씩 선택한 후 키보드의 **Delete** 키를 눌러 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-196">If there are any other nameservers listed, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span>
    
    ![NetworkSolutions-BP-Redelegate-1-5](../../media/eeb8ad22-bf4a-43a8-b97a-f09c3654d89b.png)
  
2. <span data-ttu-id="78c84-198">이름 **서버 추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="78c84-198">Select **Add More Name Servers**.</span></span>
    
    ![NetworkSolutionsBP-Redelegate-1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
3. <span data-ttu-id="78c84-200">**도메인 이름** 페이지에서 다음 표의 이름 서버 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-200">On the **Domain Names** page, type or copy and paste the nameserver values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="78c84-201">**이름 서버 1**</span><span class="sxs-lookup"><span data-stu-id="78c84-201">**Name Server 1**</span></span> <br/> |<span data-ttu-id="78c84-202">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="78c84-202">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="78c84-203">**이름 서버 2**</span><span class="sxs-lookup"><span data-stu-id="78c84-203">**Name Server 2**</span></span> <br/> |<span data-ttu-id="78c84-204">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="78c84-204">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="78c84-205">**Name Server 3**(이름 서버 3)</span><span class="sxs-lookup"><span data-stu-id="78c84-205">**Name Server 3**</span></span> <br/> |<span data-ttu-id="78c84-206">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="78c84-206">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="78c84-207">**Name Server 4**(이름 서버 4)</span><span class="sxs-lookup"><span data-stu-id="78c84-207">**Name Server 4**</span></span> <br/> |<span data-ttu-id="78c84-208">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="78c84-208">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    
![NetworkSolutionsBP-Redelegate-1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
4. <span data-ttu-id="78c84-210">DNS **이동을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="78c84-210">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-Redelegate-1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
5. <span data-ttu-id="78c84-212">변경 **내용 저장을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="78c84-212">Select **Save Changes.**</span></span>
    
    ![NetworkSolutionsBP-Redelegate-1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> <span data-ttu-id="78c84-214">이름 서버 레코드 업데이트가 인터넷의 DNS 시스템 전체에 업데이트되기까지 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-214">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="78c84-215">그런 다음 Microsoft 전자 메일 및 기타 서비스가 모두 도메인에서 작동하게 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="78c84-215">Then your Microsoft email and other services will be all set to work with your domain.</span></span>
