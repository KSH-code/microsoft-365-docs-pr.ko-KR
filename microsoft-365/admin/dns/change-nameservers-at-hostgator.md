---
title: Hostgator을 사용 하 여 Microsoft를 설정 하도록 이름 서버 변경
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
ms.assetid: f3bd3c62-0477-48e4-b2b5-21e329d67985
description: Hostgator에서 사용자 지정 도메인의 DNS 레코드를 관리 하도록 Microsoft를 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 787fe5f5e768d9d93cfca9d1644037142822216e
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400644"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-hostgator"></a><span data-ttu-id="10166-103">Hostgator을 사용 하 여 Microsoft 365을 설정 하도록 이름 서버 변경</span><span class="sxs-lookup"><span data-stu-id="10166-103">Change nameservers to set up Microsoft 365 with Hostgator</span></span>

 <span data-ttu-id="10166-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="10166-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="10166-105">Microsoft에서 DNS 레코드를 관리 하도록 하려면 다음 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="10166-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="10166-106">원하는 경우 [모든 MICROSOFT DNS 레코드를 Hostgator에서 관리할](create-dns-records-at-hostgator.md)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10166-106">(If you prefer, you can [manage all your Microsoft DNS records at Hostgator](create-dns-records-at-hostgator.md).)</span></span>
  
    
## <a name="point-your-domain-to-your-hosting-account"></a><span data-ttu-id="10166-107">도메인을 호스팅 계정에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="10166-107">Point your domain to your hosting account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="10166-108">**확인을 위해 TXT 레코드 추가** 구역의 절차를 수행하기 전에 이 절차를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10166-108">You must perform this procedure before you perform the procedure in the following section, **Add a TXT record for verification**.</span></span>
  
<span data-ttu-id="10166-109">이러한 단계에 따라 도메인 및 호스팅 계정을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="10166-109">Follow these steps to associate your domain and hosting accounts.</span></span>
  
1. <span data-ttu-id="10166-p102">시작하려면 [이 링크](https://portal.hostgator.com/domain/manage)를 사용하여 Hostgator의 고객 포털 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="10166-p102">To get started, go to your customer portal page at Hostgator by using [this link](https://portal.hostgator.com/domain/manage). You'll be prompted to log in.</span></span>
    
    ![Hostgator-BP-Redelegate-1-0](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. <span data-ttu-id="10166-113">**도메인** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10166-113">Select the **Domains** tab.</span></span>
    
    ![Hostgator-BP-Redelegate-1-1](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. <span data-ttu-id="10166-115">**도메인 관리** 페이지의 **내 도메인** 영역에서 업데이트할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10166-115">On the **Manage Domains** page, in the **My Domains** area, select the domain you want to update.</span></span>
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. <span data-ttu-id="10166-117">**도메인 개요** 페이지의 **이름 서버** 영역에서 **변경을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10166-117">On the **Domains Overview** page, in the **Name Servers** area, select **Change**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-3](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. <span data-ttu-id="10166-119">도메인의 **이름 서버** 페이지에 있는 **호스팅 계정 선택** 드롭다운 목록에서 도메인과 연결 된 **호스팅 계정을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10166-119">On the **Name Servers** page for your domain, in the **Select Hosting Account** drop-down list, choose the **hosting account** that is associated with your domain.</span></span>
    
    ![Hostgator-BP-Redelegate-1-4](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. <span data-ttu-id="10166-121">**이름 서버 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10166-121">Select **Save Name Servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-9](../../media/b52a825a-6d54-49ba-87c8-52f770fdfa0c.png)
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="10166-123">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="10166-123">Add a TXT record for verification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="10166-124">이 절차를 수행 하기 전에 먼저이 문서의 첫 번째 섹션에 나와 있는 절차를 수행 하 고 [도메인을 호스팅 계정으로](#point-your-domain-to-your-hosting-account)지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10166-124">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account.](#point-your-domain-to-your-hosting-account).</span></span>
  
<span data-ttu-id="10166-p103">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10166-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="10166-p104">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10166-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>
  
1. <span data-ttu-id="10166-p105">시작하려면 Hostgator의 cPanel 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="10166-p105">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="10166-p106">(Hostgator에서 호스팅되는 각 계정에는 고유 cPanel 주소가 할당되어 있습니다. cPanel 주소의 형식은 https://YourSiteAddress:secure-port-number와 같습니다. Hostgator에서 보낸 등록 전자 메일에 이 주소가 명시되어 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="10166-p106">(Each hosted account at Hostgator is assigned a unique cPanel address. Your cPanel address should look like this: https://YourSiteAddress:secure-port-number. The sign-up email you received from Hostgator will specify that address.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="10166-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="10166-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="10166-135">시작 하려면 Hostgator에서 호스팅 계정을 구입 하거나 [도메인의 NS (이름 서버) 레코드가](#change-your-domains-nameserver-ns-records) Microsoft를 가리키도록 변경 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10166-135">To get started, you can either purchase a hosting account from Hostgator or [change your domain's nameserver (NS) records](#change-your-domains-nameserver-ns-records) to point to Microsoft.</span></span> 
  
2. <span data-ttu-id="10166-136">**제어판** 페이지의 **도메인** 영역에서 **고급 DNS 영역 편집기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10166-136">On the **Control Panel** page, in the **Domains** area, select **Advanced DNS Zone Editor**.</span></span>
    
    <span data-ttu-id="10166-137">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="10166-137">(You may have to scroll down.)</span></span> 
    
3. <span data-ttu-id="10166-138">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="10166-138">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="10166-139">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="10166-139">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="10166-140">**이름**</span><span class="sxs-lookup"><span data-stu-id="10166-140">**Name**</span></span> <br/> |<span data-ttu-id="10166-141">**TTL**</span><span class="sxs-lookup"><span data-stu-id="10166-141">**TTL**</span></span> <br/> |<span data-ttu-id="10166-142">**종류**</span><span class="sxs-lookup"><span data-stu-id="10166-142">**Type**</span></span> <br/> |<span data-ttu-id="10166-143">**TXT 데이터**</span><span class="sxs-lookup"><span data-stu-id="10166-143">**TXT Data**</span></span> <br/> |
|<span data-ttu-id="10166-p108">사용자의  *domain_name*  (예: fourthcoffee.com)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10166-p108">Use your  *domain_name*  . (for example, fourthcoffee.com.)  </span></span><br/> <span data-ttu-id="10166-146">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="10166-146">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="10166-147">1 </span><span class="sxs-lookup"><span data-stu-id="10166-147">1</span></span>  <br/> |<span data-ttu-id="10166-148">TXT</span><span class="sxs-lookup"><span data-stu-id="10166-148">TXT</span></span>  <br/> |<span data-ttu-id="10166-149">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="10166-149">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="10166-150">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="10166-150">**Note:** This is an example.</span></span> <span data-ttu-id="10166-151">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10166-151">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="10166-152">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="10166-152">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     <br/>  |
   
4. <span data-ttu-id="10166-153">**레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10166-153">Select **Add Record**.</span></span>
    
5. <span data-ttu-id="10166-154">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="10166-154">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="10166-155">도메인 등록 기관 사이트에서 레코드를 추가 했으므로 이제 Microsoft로 이동 하 여 레코드 검색을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="10166-155">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="10166-156">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="10166-156">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="10166-157">I관리 센터에서 \*\* 설정 \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="10166-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="10166-158">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="10166-158">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="10166-159">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="10166-159">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="10166-160">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="10166-160">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="10166-161">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="10166-161">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="10166-162">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10166-162">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="10166-163">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="10166-163">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="10166-164">도메인의 NS(이름 서버) 레코드 변경</span><span class="sxs-lookup"><span data-stu-id="10166-164">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="10166-165">Microsoft에서 도메인 설정을 완료 하려면 도메인 등록 기관에서 도메인의 NS 레코드를 Microsoft 기본 및 보조 이름 서버를 가리키도록 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="10166-165">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="10166-166">이렇게 하면 Microsoft에서 도메인의 DNS 레코드를 업데이트 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="10166-166">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="10166-167">전자 메일, 비즈니스용 Skype Online, 공개 웹 사이트가 사용자의 도메인을 사용하도록 모든 레코드가 자동으로 추가되고 모든 설정이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="10166-167">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="10166-168">Microsoft 이름 서버를 가리키도록 도메인의 NS 레코드를 변경 하면 현재 도메인에 연결 된 모든 서비스가 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="10166-168">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="10166-169">예를 들어 도메인으로 전송 되는 모든 전자 메일 (rob@ *your_domain* )이 변경 된 후 Microsoft로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10166-169">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="10166-170">다음 절차에서는 목록에서 원치 않는 이름 서버를 삭제 하는 방법 및 올바른 이름 서버가 나열 되어 있지 않은 경우 추가 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="10166-170">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="10166-171">이 섹션의 단계를 완료 한 후에는 **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**및 **ns4.bdm.microsoftonline.com**와 같은 4 가지 이름 서버를 나열 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10166-171">When you have completed the steps in this section, the only nameservers that should be listed are these four:  **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**.</span></span>
  
1. <span data-ttu-id="10166-p114">시작하려면 [이 링크](https://portal.hostgator.com/domain/manage)를 사용하여 Hostgator의 고객 포털 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="10166-p114">To get started, go to your customer portal page at Hostgator by using [this link](https://portal.hostgator.com/domain/manage). You'll be prompted to log in.</span></span>
    
    ![Hostgator-BP-Redelegate-1-0](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. <span data-ttu-id="10166-175">**도메인** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10166-175">Select the **Domains** tab.</span></span> 
    
    ![Hostgator-BP-Redelegate-1-1](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. <span data-ttu-id="10166-177">**도메인 관리** 페이지의 **내 도메인** 영역에서 업데이트할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10166-177">On the **Manage Domains** page, in the **My Domains** area, select the domain you want to update.</span></span> 
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. <span data-ttu-id="10166-179">**도메인 개요** 페이지의 **이름 서버** 영역에서 **변경을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10166-179">On the **Domain Overview** page, in the **Name Servers** area, select **Change**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-3](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. <span data-ttu-id="10166-181">도메인의 **이름 서버** 페이지에 있는 **호스팅 계정 선택** 드롭다운 목록에서 도메인과 연결 된 **호스팅 계정을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10166-181">On the **Name Servers** page for your domain, in the **Select Hosting Account** drop-down list, choose the **hosting account** that is associated with your domain.</span></span> 
    
    ![Hostgator-BP-Redelegate-1-4](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. <span data-ttu-id="10166-183">**내 이름 서버 수동 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10166-183">Select **Manually set my name servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-5](../../media/5b73ae32-f26e-48aa-b5ad-6da20f1c491a.png)
  
7.   <span data-ttu-id="10166-185">**주의**: 네 가지 올바른 이름 서버 이외의 기존 이름 서버 있는 경우에만 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="10166-185">**CAUTION**: Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="10166-186">(즉, **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**또는 **ns4.bdm.microsoftonline.com**로 이름이 지정 *되지* 않은 현재 이름 서버 삭제 합니다.)</span><span class="sxs-lookup"><span data-stu-id="10166-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span>
  
        <span data-ttu-id="10166-187">계속 도메인에 대한 **이름 서버** 페이지의 이름 서버 목록에서 각 이름 서버를 선택하고 키보드에서 **Delete** 키를 눌러 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="10166-187">Still on the **Name Servers** page for your domain, in the list of nameservers, delete each nameserver in the list by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
   ![Hostgator-BP-Redelegate-1-6](../../media/fa9820e7-28bb-4792-b16c-51e54d83feb1.png)
  
8. <span data-ttu-id="10166-189">계속 이름 서버 목록에서 다음 표의 처음 두 개의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="10166-189">Still in the list of nameservers, type or copy and paste the first two values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="10166-190">**이름 서버 1:**</span><span class="sxs-lookup"><span data-stu-id="10166-190">**Name Server 1:**</span></span> <br/> |<span data-ttu-id="10166-191">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="10166-191">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="10166-192">**이름 서버 2:**</span><span class="sxs-lookup"><span data-stu-id="10166-192">**Name Server 2:**</span></span> <br/> |<span data-ttu-id="10166-193">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="10166-193">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="10166-194">**이름 서버 3:**</span><span class="sxs-lookup"><span data-stu-id="10166-194">**Name Server 3:**</span></span> <br/> |<span data-ttu-id="10166-195">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="10166-195">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="10166-196">**이름 서버 4:**</span><span class="sxs-lookup"><span data-stu-id="10166-196">**Name Server 4:**</span></span> <br/> |<span data-ttu-id="10166-197">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="10166-197">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Hostgator-BP-Redelegate-1-7-1](../../media/a8c10aa7-30b0-4bc8-9596-20256d396274.png)
  
9. <span data-ttu-id="10166-199">다른 이름 서버 값을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="10166-199">Add the other nameserver values.</span></span>
    
    <span data-ttu-id="10166-200">**(+)** 추가를 선택 하 고 표의 다음 행에 있는 값을 레코드의 상자에 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="10166-200">Select **(+)** add, and then type or copy and paste the value from the next row of the table into the box for the record.</span></span> 
    
    <span data-ttu-id="10166-201">4개의 이름 서버 레코드를 모두 만들 때까지 이 과정을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="10166-201">Repeat this process until you have created all four nameserver records.</span></span>
    
    ![Hostgator-BP-Redelegate-1-7-2](../../media/92159a39-e498-4220-9b0d-ae2e718c7fb9.png)
  
10. <span data-ttu-id="10166-203">**이름 서버 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10166-203">Select **Save Name Servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-8](../../media/bd6b0dfa-5d39-4805-970d-7ab153cff117.png)
  
> [!NOTE]
> <span data-ttu-id="10166-205">이름 서버 레코드 업데이트가 인터넷의 DNS 시스템 전체에 업데이트되기까지 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10166-205">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="10166-206">그러면 Microsoft 전자 메일 및 기타 서비스가 모두 도메인에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10166-206">Then your Microsoft email and other services will be all set to work with your domain.</span></span>
