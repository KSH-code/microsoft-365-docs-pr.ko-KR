---
title: Hostgator에서 이름 서버를 변경하여 Office 365 설정
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f3bd3c62-0477-48e4-b2b5-21e329d67985
description: Hostgator에서 사용자 지정 도메인의 DNS 레코드를 관리 하기 위해 Office 365을 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: d592fc77513107679206a4ac187116c7d6fb794f
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212332"
---
# <a name="change-nameservers-to-set-up-office-365-with-hostgator"></a><span data-ttu-id="5d856-103">Hostgator에서 이름 서버를 변경하여 Office 365 설정</span><span class="sxs-lookup"><span data-stu-id="5d856-103">Change nameservers to set up Office 365 with Hostgator</span></span>

 <span data-ttu-id="5d856-104">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="5d856-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="5d856-p101">Office 365에서 Office 365 DNS 레코드를 관리하도록 하려면 다음 지침을 따릅니다. 원하는 경우 [모든 Office 365 DNS 레코드를 Hostgator에서 관리](create-dns-records-at-hostgator.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Hostgator](create-dns-records-at-hostgator.md).)</span></span>
  
    
## <a name="point-your-domain-to-your-hosting-account"></a><span data-ttu-id="5d856-107">도메인을 호스팅 계정에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-107">Point your domain to your hosting account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d856-108">**확인을 위해 TXT 레코드 추가** 구역의 절차를 수행하기 전에 이 절차를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-108">You must perform this procedure before you perform the procedure in the following section, **Add a TXT record for verification**.</span></span>
  
<span data-ttu-id="5d856-109">이러한 단계에 따라 도메인 및 호스팅 계정을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-109">Follow these steps to associate your domain and hosting accounts.</span></span>
  
1. <span data-ttu-id="5d856-p102">시작하려면 [이 링크](https://portal.hostgator.com/domain/manage)를 사용하여 Hostgator의 고객 포털 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-p102">To get started, go to your customer portal page at Hostgator by using [this link](https://portal.hostgator.com/domain/manage). You'll be prompted to log in.</span></span>
    
    ![Hostgator-BP-Redelegate-1-0](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. <span data-ttu-id="5d856-113">**도메인** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-113">Select the **Domains** tab.</span></span>
    
    ![Hostgator-BP-Redelegate-1-1](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. <span data-ttu-id="5d856-115">**도메인 관리** 페이지의 **내 도메인** 영역에서 업데이트할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-115">On the **Manage Domains** page, in the **My Domains** area, select the domain you want to update.</span></span>
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. <span data-ttu-id="5d856-117">**도메인 개요** 페이지의 **이름 서버** 영역에서 **변경을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-117">On the **Domains Overview** page, in the **Name Servers** area, select **Change**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-3](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. <span data-ttu-id="5d856-119">도메인의 **이름 서버** 페이지에 있는 **호스팅 계정 선택** 드롭다운 목록에서 도메인과 연결 된 **호스팅 계정을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-119">On the **Name Servers** page for your domain, in the **Select Hosting Account** drop-down list, choose the **hosting account** that is associated with your domain.</span></span>
    
    ![Hostgator-BP-Redelegate-1-4](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. <span data-ttu-id="5d856-121">**이름 서버 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-121">Select **Save Name Servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-9](../../media/b52a825a-6d54-49ba-87c8-52f770fdfa0c.png)
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="5d856-123">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="5d856-123">Add a TXT record for verification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d856-124">이 절차를 수행 하기 전에 먼저이 문서의 첫 번째 섹션에 나와 있는 절차를 수행 하 고 [도메인을 호스팅 계정으로](#point-your-domain-to-your-hosting-account)지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-124">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account.](#point-your-domain-to-your-hosting-account).</span></span>
  
<span data-ttu-id="5d856-p103">Office 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Office 365에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5d856-p104">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>
  
1. <span data-ttu-id="5d856-p105">시작하려면 Hostgator의 cPanel 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-p105">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="5d856-p106">(Hostgator에서 호스팅되는 각 계정에는 고유 cPanel 주소가 할당되어 있습니다. cPanel 주소의 형식은 https://YourSiteAddress:secure-port-number와 같습니다. Hostgator에서 보낸 등록 전자 메일에 이 주소가 명시되어 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="5d856-p106">(Each hosted account at Hostgator is assigned a unique cPanel address. Your cPanel address should look like this: https://YourSiteAddress:secure-port-number. The sign-up email you received from Hostgator will specify that address.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5d856-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="5d856-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="5d856-135">Office 365을 시작 하려면 Hostgator에서 호스팅 계정을 구입 하거나 [도메인의 NS (이름 서버) 레코드](#change-your-domains-nameserver-ns-records) 를 Office 365를 가리키도록 변경 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-135">To get started with Office 365, you can either purchase a hosting account from Hostgator or [change your domain's nameserver (NS) records](#change-your-domains-nameserver-ns-records) to point to Office 365.</span></span> 
  
2. <span data-ttu-id="5d856-136">**제어판** 페이지의 **도메인** 영역에서 **고급 DNS 영역 편집기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-136">On the **Control Panel** page, in the **Domains** area, select **Advanced DNS Zone Editor**.</span></span>
    
    <span data-ttu-id="5d856-137">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="5d856-137">(You may have to scroll down.)</span></span> 
    
3. <span data-ttu-id="5d856-138">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="5d856-138">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="5d856-139">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="5d856-139">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5d856-140">**이름**</span><span class="sxs-lookup"><span data-stu-id="5d856-140">**Name**</span></span> <br/> |<span data-ttu-id="5d856-141">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5d856-141">**TTL**</span></span> <br/> |<span data-ttu-id="5d856-142">**종류**</span><span class="sxs-lookup"><span data-stu-id="5d856-142">**Type**</span></span> <br/> |<span data-ttu-id="5d856-143">**TXT 데이터**</span><span class="sxs-lookup"><span data-stu-id="5d856-143">**TXT Data**</span></span> <br/> |
|<span data-ttu-id="5d856-p108">사용자의  *domain_name*  (예: fourthcoffee.com)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-p108">Use your  *domain_name*  . (for example, fourthcoffee.com.)  </span></span><br/> <span data-ttu-id="5d856-146">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d856-146">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5d856-147">1 </span><span class="sxs-lookup"><span data-stu-id="5d856-147">1</span></span>  <br/> |<span data-ttu-id="5d856-148">TXT</span><span class="sxs-lookup"><span data-stu-id="5d856-148">TXT</span></span>  <br/> |<span data-ttu-id="5d856-149">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="5d856-149">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="5d856-150">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-150">**Note:** This is an example.</span></span> <span data-ttu-id="5d856-151">여기에는 Office 365의 표에 있는 특정 **보낼 대상 또는 지점** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-151">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="5d856-152">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="5d856-152">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     <br/>  |
   
4. <span data-ttu-id="5d856-153">**레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-153">Select **Add Record**.</span></span>
    
5. <span data-ttu-id="5d856-154">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-154">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="5d856-155">이제 도메인 등록 기관에 레코드가 추가되었습니다. Office 365로 돌아가서 Office 365에 레코드를 찾을 것을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-155">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="5d856-156">Office 365에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-156">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="5d856-157">I관리 센터에서 \*\* 설정 \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="5d856-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="5d856-158">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-158">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="5d856-159">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-159">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="5d856-160">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-160">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5d856-161">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="5d856-161">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="5d856-162">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-162">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="5d856-163">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [Office 365에서 도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5d856-163">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="5d856-164">도메인의 NS(이름 서버) 레코드 변경</span><span class="sxs-lookup"><span data-stu-id="5d856-164">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="5d856-p111">Office 365에서 도메인 설정을 완료하려면 도메인 등록 기관에서 도메인의 NS 레코드가 Office 365 기본 및 보조 이름 서버를 가리키도록 변경합니다. 이렇게 하면 Office 365가 사용자 대신 도메인의 DNS 레코드를 업데이트하도록 설정됩니다. 전자 메일, 비즈니스용 Skype Online, 공개 웹 사이트가 사용자의 도메인을 사용하도록 모든 레코드가 자동으로 추가되고 모든 설정이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-p111">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="5d856-p112">Office 365 이름 서버를 가리키도록 도메인 NS 레코드를 변경하면 현재 도메인에 연결되는 모든 서비스가 영향을 받습니다. 예를 들어 이 변경 내용을 적용하면 사용자의 도메인(예: rob@ *사용자_도메인*  .com)으로 보낸 전자 메일이 Office 365로 수신됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-p112">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5d856-170">다음 절차에서는 목록에서 원치 않는 이름 서버를 삭제 하는 방법 및 올바른 이름 서버가 나열 되어 있지 않은 경우 추가 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-170">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="5d856-171">이 섹션의 단계를 완료 한 후에는 **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**및 **ns4.bdm.microsoftonline.com**와 같은 4 가지 이름 서버를 나열 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-171">When you have completed the steps in this section, the only nameservers that should be listed are these four:  **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**.</span></span>
  
1. <span data-ttu-id="5d856-p114">시작하려면 [이 링크](https://portal.hostgator.com/domain/manage)를 사용하여 Hostgator의 고객 포털 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-p114">To get started, go to your customer portal page at Hostgator by using [this link](https://portal.hostgator.com/domain/manage). You'll be prompted to log in.</span></span>
    
    ![Hostgator-BP-Redelegate-1-0](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. <span data-ttu-id="5d856-175">**도메인** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-175">Select the **Domains** tab.</span></span> 
    
    ![Hostgator-BP-Redelegate-1-1](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. <span data-ttu-id="5d856-177">**도메인 관리** 페이지의 **내 도메인** 영역에서 업데이트할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-177">On the **Manage Domains** page, in the **My Domains** area, select the domain you want to update.</span></span> 
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. <span data-ttu-id="5d856-179">**도메인 개요** 페이지의 **이름 서버** 영역에서 **변경을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-179">On the **Domain Overview** page, in the **Name Servers** area, select **Change**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-3](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. <span data-ttu-id="5d856-181">도메인의 **이름 서버** 페이지에 있는 **호스팅 계정 선택** 드롭다운 목록에서 도메인과 연결 된 **호스팅 계정을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-181">On the **Name Servers** page for your domain, in the **Select Hosting Account** drop-down list, choose the **hosting account** that is associated with your domain.</span></span> 
    
    ![Hostgator-BP-Redelegate-1-4](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. <span data-ttu-id="5d856-183">**내 이름 서버 수동 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-183">Select **Manually set my name servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-5](../../media/5b73ae32-f26e-48aa-b5ad-6da20f1c491a.png)
  
7.   <span data-ttu-id="5d856-185">**주의**: 네 가지 올바른 이름 서버 이외의 기존 이름 서버 있는 경우에만 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-185">**CAUTION**: Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="5d856-186">(즉, **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**또는 **ns4.bdm.microsoftonline.com**로 이름이 지정 *되지* 않은 현재 이름 서버 삭제 합니다.)</span><span class="sxs-lookup"><span data-stu-id="5d856-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span>
  
        <span data-ttu-id="5d856-187">계속 도메인에 대한 **이름 서버** 페이지의 이름 서버 목록에서 각 이름 서버를 선택하고 키보드에서 **Delete** 키를 눌러 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-187">Still on the **Name Servers** page for your domain, in the list of nameservers, delete each nameserver in the list by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
   ![Hostgator-BP-Redelegate-1-6](../../media/fa9820e7-28bb-4792-b16c-51e54d83feb1.png)
  
8. <span data-ttu-id="5d856-189">계속 이름 서버 목록에서 다음 표의 처음 두 개의 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-189">Still in the list of nameservers, type or copy and paste the first two values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="5d856-190">**이름 서버 1:**</span><span class="sxs-lookup"><span data-stu-id="5d856-190">**Name Server 1:**</span></span> <br/> |<span data-ttu-id="5d856-191">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="5d856-191">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="5d856-192">**이름 서버 2:**</span><span class="sxs-lookup"><span data-stu-id="5d856-192">**Name Server 2:**</span></span> <br/> |<span data-ttu-id="5d856-193">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="5d856-193">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="5d856-194">**이름 서버 3:**</span><span class="sxs-lookup"><span data-stu-id="5d856-194">**Name Server 3:**</span></span> <br/> |<span data-ttu-id="5d856-195">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="5d856-195">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="5d856-196">**이름 서버 4:**</span><span class="sxs-lookup"><span data-stu-id="5d856-196">**Name Server 4:**</span></span> <br/> |<span data-ttu-id="5d856-197">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="5d856-197">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Hostgator-BP-Redelegate-1-7-1](../../media/a8c10aa7-30b0-4bc8-9596-20256d396274.png)
  
9. <span data-ttu-id="5d856-199">다른 이름 서버 값을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-199">Add the other nameserver values.</span></span>
    
    <span data-ttu-id="5d856-200">**(+)** 추가를 선택 하 고 표의 다음 행에 있는 값을 레코드의 상자에 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-200">Select **(+)** add, and then type or copy and paste the value from the next row of the table into the box for the record.</span></span> 
    
    <span data-ttu-id="5d856-201">4개의 이름 서버 레코드를 모두 만들 때까지 이 과정을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-201">Repeat this process until you have created all four nameserver records.</span></span>
    
    ![Hostgator-BP-Redelegate-1-7-2](../../media/92159a39-e498-4220-9b0d-ae2e718c7fb9.png)
  
10. <span data-ttu-id="5d856-203">**이름 서버 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-203">Select **Save Name Servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-8](../../media/bd6b0dfa-5d39-4805-970d-7ab153cff117.png)
  
> [!NOTE]
> <span data-ttu-id="5d856-p116">이름 서버 레코드 업데이트가 인터넷의 DNS 시스템 전체에 업데이트되기까지 몇 시간이 걸릴 수 있습니다. 그 후에는 Office 365 전자 메일 및 기타 서비스가 모두 사용자의 도메인을 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d856-p116">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span>
