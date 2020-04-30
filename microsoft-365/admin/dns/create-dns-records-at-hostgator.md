---
title: Hostgator에서 Microsoft에 대 한 DNS 레코드 만들기
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
ms.assetid: 5f0c840e-4140-4571-88ed-cf235ff142d6
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대 한 DNS 레코드를 Microsoft 용 Hostgator에 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: d2d8d535d137ca3de2fc6dfc04abe8cf61dda07d
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939194"
---
# <a name="create-dns-records-at-hostgator-for-microsoft"></a><span data-ttu-id="87b9f-103">Hostgator에서 Microsoft에 대 한 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="87b9f-103">Create DNS records at Hostgator for Microsoft</span></span>

 <span data-ttu-id="87b9f-104">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="87b9f-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="87b9f-105">DNS 호스팅 공급자로 Hostgator를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-105">If Hostgator is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="87b9f-106">이 문서의 다른 절차를 사용 하 여 DNS 레코드를 추가 하기 전에 첫 번째 procedurebelow를 수행 하 여 [호스팅 계정에 대 한 도메인을 가리키도록](#point-your-domain-to-your-hosting-account)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-106">You must perform the first procedurebelow, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account), before you add DNS records by using any of the other procedures in this article.</span></span> 

<span data-ttu-id="87b9f-107">Hostgator에서 이러한 모든 변경 작업을 수행한 후에는 도메인이 Microsoft 서비스에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-107">After you make all of these changes at Hostgator, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="87b9f-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="87b9f-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="87b9f-109">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="87b9f-110">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87b9f-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="point-your-domain-to-your-hosting-account"></a><span data-ttu-id="87b9f-111">도메인을 호스팅 계정에 연결</span><span class="sxs-lookup"><span data-stu-id="87b9f-111">Point your domain to your hosting account</span></span>
<span data-ttu-id="87b9f-112"><a name="BKMK_PointDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="87b9f-112"><a name="BKMK_PointDomain"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="87b9f-113">이 문서의 다른 절차를 수행하기 전에 이 절차를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-113">You must perform this procedure before you perform any of the other procedures in this article.</span></span> 
  
<span data-ttu-id="87b9f-114">이러한 단계에 따라 도메인 및 호스팅 계정을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-114">Follow these steps to associate your domain and hosting accounts.</span></span>
  
1. <span data-ttu-id="87b9f-p102">시작하려면 [이 링크](https://portal.hostgator.com/)를 사용하여 Hostgator의 도메인 관리 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-p102">To get started, go to your domain management page at Hostgator by using [this link](https://portal.hostgator.com/). You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="87b9f-117">왼쪽에서 **도메인** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-117">Select **Domains** on the left.</span></span>
  
3. <span data-ttu-id="87b9f-118">**도메인 관리** 페이지에서 업데이트 하려는 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-118">On the **Manage Domains** page, select the domain you want to update.</span></span> 
  
4. <span data-ttu-id="87b9f-119">왼쪽의 팝업 메뉴에서 **이름 서버**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-119">On the pop-out menu on the left, select **Name Servers**.</span></span>
  
5. <span data-ttu-id="87b9f-120">도메인의 **이름 서버** 페이지에 있는 **이 도메인을 내 호스팅 계정으로 자동 가리키기** 드롭다운 목록에서 도메인과 연결 된 호스팅 계정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-120">On the **Name Servers** page for your domain, in the **Automatically point this domain to my hosting account** drop-down list, choose the hosting account that is associated with your domain.</span></span> 
  
6. <span data-ttu-id="87b9f-121">**이름 서버 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-121">Select **Save Name Servers**.</span></span>
    
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="87b9f-122">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="87b9f-122">Add a TXT record for verification</span></span>
<span data-ttu-id="87b9f-123"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="87b9f-123"><a name="BKMK_verify"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="87b9f-124">이 절차를 수행하기 전에 이 문서의 첫 번째 구역에 있는 절차, [도메인을 호스팅 계정에 연결](#point-your-domain-to-your-hosting-account)을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-124">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
<span data-ttu-id="87b9f-p103">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="87b9f-p104">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="87b9f-129">To get started, go to your cPanel page at Hostgator.</span><span class="sxs-lookup"><span data-stu-id="87b9f-129">To get started, go to your cPanel page at Hostgator.</span></span> <span data-ttu-id="87b9f-130">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="87b9f-130">You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="87b9f-131">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="87b9f-131">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="87b9f-132">cPanel 주소의 형식은 https://YourSiteAddress:secure-port-number와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-132">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="87b9f-133">Hostgator에서 받은 등록 전자 메일에는 해당 주소가 지정 되 고, **호스팅** 페이지 에서도 cpanel 링크를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-133">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="87b9f-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="87b9f-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="87b9f-135">Microsoft를 시작 하려면 Hostgator 또는 redelegate에서 호스팅 계정을 구입 [하 여 microsoft를 가리키도록](change-nameservers-at-hostgator.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-135">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="87b9f-136">**제어판** 페이지의 **도메인** 영역에서 **고급 영역 편집기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-136">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="87b9f-137">**고급 영역 편집기** 페이지의 **레코드 추가** 영역에서 새 레코드 용 상자에 다음 표의 값을 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-137">On the **Advanced Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="87b9f-138">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="87b9f-138">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="87b9f-139">**이름**</span><span class="sxs-lookup"><span data-stu-id="87b9f-139">**Name**</span></span> <br/> |<span data-ttu-id="87b9f-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="87b9f-140">**TTL**</span></span> <br/> |<span data-ttu-id="87b9f-141">**유형**</span><span class="sxs-lookup"><span data-stu-id="87b9f-141">**Type**</span></span> <br/> |<span data-ttu-id="87b9f-142">**TXT 데이터**</span><span class="sxs-lookup"><span data-stu-id="87b9f-142">**TXT Data**</span></span> <br/> |
    |<span data-ttu-id="87b9f-143">*Domain_name*를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-143">Use your  *domain_name*.</span></span> <span data-ttu-id="87b9f-144">(for example, fourthcoffee.com.)</span><span class="sxs-lookup"><span data-stu-id="87b9f-144">(for example, fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="87b9f-145">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="87b9f-145">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="87b9f-146">1 </span><span class="sxs-lookup"><span data-stu-id="87b9f-146">1</span></span>  <br/> |<span data-ttu-id="87b9f-147">TXT</span><span class="sxs-lookup"><span data-stu-id="87b9f-147">TXT</span></span>  <br/> |<span data-ttu-id="87b9f-148">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="87b9f-148">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="87b9f-149">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-149">**Note:** This is an example.</span></span> <span data-ttu-id="87b9f-150">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-150">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="87b9f-151">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="87b9f-151">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="87b9f-152">**레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-152">Select **Add Record**.</span></span>
    
5. <span data-ttu-id="87b9f-153">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-153">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="87b9f-154">이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-154">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="87b9f-155">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-155">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="87b9f-156">I관리 센터에서 \*\* 설정 \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="87b9f-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="87b9f-157">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="87b9f-158">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-158">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="87b9f-159">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-159">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="87b9f-160">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="87b9f-160">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="87b9f-161">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-161">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="87b9f-162">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87b9f-162">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="87b9f-163">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="87b9f-163">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="87b9f-164"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="87b9f-164"><a name="BKMK_add_MX"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="87b9f-165">이 절차를 수행하기 전에 이 문서의 첫 번째 구역에 있는 절차, [도메인을 호스팅 계정에 연결](#point-your-domain-to-your-hosting-account)을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-165">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="87b9f-p111">시작하려면 Hostgator의 cPanel 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-p111">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="87b9f-168">(Hostgator에서 호스팅되는 각 계정에는 고유 cPanel 주소가 할당되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-168">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="87b9f-169">cPanel 주소의 형식은 https://YourSiteAddress:secure-port-number와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-169">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="87b9f-170">Hostgator에서 받은 등록 전자 메일에는 해당 주소가 지정 되 고, **호스팅** 페이지 에서도 cpanel 링크를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-170">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="87b9f-171">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="87b9f-171">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="87b9f-172">Microsoft를 시작 하려면 Hostgator 또는 redelegate에서 호스팅 계정을 구입 [하 여 microsoft를 가리키도록](change-nameservers-at-hostgator.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-172">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="87b9f-173">**제어판** 페이지의 **전자 메일** 영역에서 **MX 항목**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-173">On the **Control Panel** page, in the **Email** area, select **MX Entry**.</span></span>
    
 
3. <span data-ttu-id="87b9f-174">**전자 메일 라우팅** 영역에서 **원격 메일 교환기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-174">In the **Email Routing** area, select **Remote Mail Exchanger**.</span></span>

4. <span data-ttu-id="87b9f-175">**변경을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-175">Select **Change**.</span></span>
  
5. <span data-ttu-id="87b9f-176">**새 레코드 추가** 영역의 새 레코드 용 상자에 다음 표의 값을 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-176">In the **Add a New Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="87b9f-177">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="87b9f-177">**Priority**</span></span>|<span data-ttu-id="87b9f-178">**대상**</span><span class="sxs-lookup"><span data-stu-id="87b9f-178">**Destination**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="87b9f-179">개</span><span class="sxs-lookup"><span data-stu-id="87b9f-179">0</span></span>  <br/> <span data-ttu-id="87b9f-180">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87b9f-180">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="87b9f-181">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="87b9f-181">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="87b9f-182">**참고:** \< Microsoft 계정에서 *도메인 키* \> 를 가져옵니다.  </span><span class="sxs-lookup"><span data-stu-id="87b9f-182">**Note:** Get your \< *domain-key*  \> from your Microsoft account.</span></span>  [<span data-ttu-id="87b9f-183">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="87b9f-183">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
  
6. <span data-ttu-id="87b9f-184">**새 레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-184">Select **Add New Record**.</span></span>
   
 
7. <span data-ttu-id="87b9f-185">**Mx 레코드** 구역에 다른 mx 레코드가 있으면 각 레코드를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-185">If there are any other MX records in the **MX Records** section, remove each of them.</span></span> 

    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="87b9f-186">Microsoft에 필요한 6 개의 CNAME 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-186">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="87b9f-187"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="87b9f-187"><a name="BKMK_add_CNAME"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="87b9f-188">이 절차를 수행하기 전에 이 문서의 첫 번째 구역에 있는 절차, [도메인을 호스팅 계정에 연결](#point-your-domain-to-your-hosting-account)을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-188">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="87b9f-p115">시작하려면 Hostgator의 cPanel 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-p115">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="87b9f-191">(Hostgator에서 호스팅되는 각 계정에는 고유 cPanel 주소가 할당되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-191">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="87b9f-192">cPanel 주소의 형식은 https://YourSiteAddress:secure-port-number와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-192">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="87b9f-193">Hostgator에서 받은 등록 전자 메일에는 해당 주소가 지정 되 고, **호스팅** 페이지 에서도 cpanel 링크를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-193">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="87b9f-194">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="87b9f-194">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="87b9f-195">Microsoft를 시작 하려면 Hostgator 또는 redelegate에서 호스팅 계정을 구입 [하 여 microsoft를 가리키도록](change-nameservers-at-hostgator.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-195">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="87b9f-196">**제어판** 페이지의 **도메인** 영역에서 **고급 영역 편집기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-196">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="87b9f-197">6개의 CNAME 레코드 중 첫 번째 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-197">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="87b9f-198">**고급 영역 편집기** 페이지의 **레코드 추가** 영역의 새 레코드 용 상자에 다음 표에 있는 첫 번째 행의 값을 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-198">On the **Advanced Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="87b9f-199">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="87b9f-199">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="87b9f-200">**이름**</span><span class="sxs-lookup"><span data-stu-id="87b9f-200">**Name**</span></span>|<span data-ttu-id="87b9f-201">**TTL**</span><span class="sxs-lookup"><span data-stu-id="87b9f-201">**TTL**</span></span>|<span data-ttu-id="87b9f-202">**종류**</span><span class="sxs-lookup"><span data-stu-id="87b9f-202">**Type**</span></span>|<span data-ttu-id="87b9f-203">**CNAME**</span><span class="sxs-lookup"><span data-stu-id="87b9f-203">**CNAME**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="87b9f-204">autodiscover.</span><span class="sxs-lookup"><span data-stu-id="87b9f-204">autodiscover.</span></span> <span data-ttu-id="87b9f-205">*domain_name*합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-205">*domain_name*.</span></span> <span data-ttu-id="87b9f-206">(예: autodiscover.fourthcoffee.com)</span><span class="sxs-lookup"><span data-stu-id="87b9f-206">(for example, autodiscover.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="87b9f-207">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="87b9f-207">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="87b9f-208">3600</span><span class="sxs-lookup"><span data-stu-id="87b9f-208">3600</span></span>  <br/> |<span data-ttu-id="87b9f-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="87b9f-209">CNAME</span></span>  <br/> |<span data-ttu-id="87b9f-210">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="87b9f-210">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="87b9f-211">sip.</span><span class="sxs-lookup"><span data-stu-id="87b9f-211">sip.</span></span> <span data-ttu-id="87b9f-212">*domain_name*합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-212">*domain_name*.</span></span> <span data-ttu-id="87b9f-213">(예: sip.fourthcoffee.com)</span><span class="sxs-lookup"><span data-stu-id="87b9f-213">(for example, sip.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="87b9f-214">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="87b9f-214">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="87b9f-215">3600</span><span class="sxs-lookup"><span data-stu-id="87b9f-215">3600</span></span>  <br/> |<span data-ttu-id="87b9f-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="87b9f-216">CNAME</span></span>  <br/> |<span data-ttu-id="87b9f-217">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="87b9f-217">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="87b9f-218">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="87b9f-218">lyncdiscover.</span></span> <span data-ttu-id="87b9f-219">*domain_name*합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-219">*domain_name*.</span></span> <span data-ttu-id="87b9f-220">(예: lyncdiscover.fourthcoffee.com)</span><span class="sxs-lookup"><span data-stu-id="87b9f-220">(for example, lyncdiscover.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="87b9f-221">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="87b9f-221">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="87b9f-222">3600</span><span class="sxs-lookup"><span data-stu-id="87b9f-222">3600</span></span>  <br/> |<span data-ttu-id="87b9f-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="87b9f-223">CNAME</span></span>  <br/> |<span data-ttu-id="87b9f-224">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="87b9f-224">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="87b9f-225">enterpriseregistration.</span><span class="sxs-lookup"><span data-stu-id="87b9f-225">enterpriseregistration.</span></span> <span data-ttu-id="87b9f-226">*domain_name*합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-226">*domain_name*.</span></span> <span data-ttu-id="87b9f-227">(예: enterpriseregistration.fourthcoffee.com)</span><span class="sxs-lookup"><span data-stu-id="87b9f-227">(for example, enterpriseregistration.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="87b9f-228">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="87b9f-228">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="87b9f-229">3600</span><span class="sxs-lookup"><span data-stu-id="87b9f-229">3600</span></span>  <br/> |<span data-ttu-id="87b9f-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="87b9f-230">CNAME</span></span>  <br/> |<span data-ttu-id="87b9f-231">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="87b9f-231">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="87b9f-232">enterpriseenrollment.</span><span class="sxs-lookup"><span data-stu-id="87b9f-232">enterpriseenrollment.</span></span> <span data-ttu-id="87b9f-233">*domain_name*합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-233">*domain_name*.</span></span> <span data-ttu-id="87b9f-234">(예: enterpriseregistration.fourthcoffee.com)</span><span class="sxs-lookup"><span data-stu-id="87b9f-234">(for example, enterpriseregistration.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="87b9f-235">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="87b9f-235">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="87b9f-236">3600</span><span class="sxs-lookup"><span data-stu-id="87b9f-236">3600</span></span>  <br/> |<span data-ttu-id="87b9f-237">CNAME</span><span class="sxs-lookup"><span data-stu-id="87b9f-237">CNAME</span></span>  <br/> |<span data-ttu-id="87b9f-238">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="87b9f-238">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |

  
4. <span data-ttu-id="87b9f-239">**레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-239">Select **Add Record**.</span></span>

5. <span data-ttu-id="87b9f-240">나머지 5개의 CNAME 레코드를 각각 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-240">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="87b9f-241">**레코드 추가** 구역에서 표의 다음 행 값을 사용 하 여 레코드를 만들고 다시 **레코드 추가** 를 선택 하 여 해당 레코드를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-241">In the **Add a Record** section, create a record by using the values from the next row in the table, and then again select **Add Record** to complete that record.</span></span> 
    
    <span data-ttu-id="87b9f-242">6개의 CNAME 레코드를 모두 만들 때까지 이 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-242">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="87b9f-243">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="87b9f-243">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="87b9f-244"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="87b9f-244"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="87b9f-245">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-245">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="87b9f-246">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-246">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="87b9f-247">도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="87b9f-247">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="87b9f-248">대신, 필수 Microsoft 값을 현재 레코드에 추가하여 두 값 집합을 모두 포함하는 단일 SPF 레코드가 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-248">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="87b9f-249">예제가 필요하세요?</span><span class="sxs-lookup"><span data-stu-id="87b9f-249">Need examples?</span></span> <span data-ttu-id="87b9f-250">[Microsoft에 대한 외부 Domain Name System 레코드](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87b9f-250">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="87b9f-251">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="87b9f-251">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="87b9f-252">이 절차를 수행하기 전에 이 문서의 첫 번째 구역에 있는 절차, [도메인을 호스팅 계정에 연결](#point-your-domain-to-your-hosting-account)을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-252">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="87b9f-p124">시작하려면 Hostgator의 cPanel 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-p124">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="87b9f-255">(Hostgator에서 호스팅되는 각 계정에는 고유 cPanel 주소가 할당되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-255">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="87b9f-256">cPanel 주소의 형식은 https://YourSiteAddress:secure-port-number와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-256">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="87b9f-257">Hostgator에서 받은 등록 전자 메일에는 해당 주소가 지정 되 고, **호스팅** 페이지 에서도 cpanel 링크를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-257">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="87b9f-258">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="87b9f-258">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="87b9f-259">Microsoft를 시작 하려면 Hostgator 또는 redelegate에서 호스팅 계정을 구입 [하 여 microsoft를 가리키도록](change-nameservers-at-hostgator.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-259">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="87b9f-260">**제어판** 페이지의 **도메인** 영역에서 **고급 영역 편집기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-260">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="87b9f-261">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="87b9f-261">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="87b9f-262">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="87b9f-262">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="87b9f-263">**이름**</span><span class="sxs-lookup"><span data-stu-id="87b9f-263">**Name**</span></span>|<span data-ttu-id="87b9f-264">**TTL**</span><span class="sxs-lookup"><span data-stu-id="87b9f-264">**TTL**</span></span>|<span data-ttu-id="87b9f-265">**유형**</span><span class="sxs-lookup"><span data-stu-id="87b9f-265">**Type**</span></span>|<span data-ttu-id="87b9f-266">**TXT 데이터**</span><span class="sxs-lookup"><span data-stu-id="87b9f-266">**TXT Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="87b9f-267">*Domain_name*를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-267">Use your  *domain_name*.</span></span> <span data-ttu-id="87b9f-268">(for example, fourthcoffee.com.)</span><span class="sxs-lookup"><span data-stu-id="87b9f-268">(for example, fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="87b9f-269">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="87b9f-269">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="87b9f-270">3600</span><span class="sxs-lookup"><span data-stu-id="87b9f-270">3600</span></span>  <br/> |<span data-ttu-id="87b9f-271">TXT</span><span class="sxs-lookup"><span data-stu-id="87b9f-271">TXT</span></span>  <br/> |<span data-ttu-id="87b9f-272">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="87b9f-272">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="87b9f-273">\*\*참고: \*\* 모든 간격이 올바르게 유지되도록 이 항목을 복사하여 붙여넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-273">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
  
4. <span data-ttu-id="87b9f-274">**레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-274">Select **Add Record**.</span></span>
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="87b9f-275">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="87b9f-275">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="87b9f-276"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="87b9f-276"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="87b9f-277">이 절차를 수행하기 전에 이 문서의 첫 번째 구역에 있는 절차, [도메인을 호스팅 계정에 연결](#point-your-domain-to-your-hosting-account)을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-277">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="87b9f-p128">시작하려면 Hostgator의 cPanel 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-p128">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="87b9f-280">(Hostgator에서 호스팅되는 각 계정에는 고유 cPanel 주소가 할당되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-280">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="87b9f-281">cPanel 주소의 형식은 https://YourSiteAddress:secure-port-number와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-281">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="87b9f-282">Hostgator에서 받은 등록 전자 메일에는 해당 주소가 지정 되 고, **호스팅** 페이지 에서도 cpanel 링크를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-282">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="87b9f-283">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="87b9f-283">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="87b9f-284">Microsoft를 시작 하려면 Hostgator 또는 redelegate에서 호스팅 계정을 구입 [하 여 microsoft를 가리키도록](change-nameservers-at-hostgator.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-284">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="87b9f-285">**제어판** 페이지의 **도메인** 영역에서 **고급 영역 편집기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-285">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>

    
3. <span data-ttu-id="87b9f-286">2개의 SRV 레코드 중 첫 번째 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-286">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="87b9f-287">**고급 DNS 영역 편집기** 페이지의 **레코드 추가** 영역에서 새 레코드용 상자에 다음 표의 첫 번째 행 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-287">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="87b9f-288">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="87b9f-288">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="87b9f-289">**이름**</span><span class="sxs-lookup"><span data-stu-id="87b9f-289">**Name**</span></span>|<span data-ttu-id="87b9f-290">**TTL**</span><span class="sxs-lookup"><span data-stu-id="87b9f-290">**TTL**</span></span>|<span data-ttu-id="87b9f-291">**종류**</span><span class="sxs-lookup"><span data-stu-id="87b9f-291">**Type**</span></span>|<span data-ttu-id="87b9f-292">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="87b9f-292">**Priority**</span></span>|<span data-ttu-id="87b9f-293">**Weight(가중치)**</span><span class="sxs-lookup"><span data-stu-id="87b9f-293">**Weight**</span></span>|<span data-ttu-id="87b9f-294">**Port(포트)**</span><span class="sxs-lookup"><span data-stu-id="87b9f-294">**Port**</span></span>|<span data-ttu-id="87b9f-295">**대상**</span><span class="sxs-lookup"><span data-stu-id="87b9f-295">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="87b9f-296">_tls을 _sip 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-296">_sip._tls.</span></span> <span data-ttu-id="87b9f-297">*domain_name*합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-297">*domain_name*.</span></span> <span data-ttu-id="87b9f-298">예를 들어 fourthcoffee를 _tls _sip 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-298">(for example, _sip._tls.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="87b9f-299">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="87b9f-299">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="87b9f-300">3600</span><span class="sxs-lookup"><span data-stu-id="87b9f-300">3600</span></span>  <br/> |<span data-ttu-id="87b9f-301">SRV</span><span class="sxs-lookup"><span data-stu-id="87b9f-301">SRV</span></span>  <br/> |<span data-ttu-id="87b9f-302">100</span><span class="sxs-lookup"><span data-stu-id="87b9f-302">100</span></span>  <br/> |<span data-ttu-id="87b9f-303">1 </span><span class="sxs-lookup"><span data-stu-id="87b9f-303">1</span></span>  <br/> |<span data-ttu-id="87b9f-304">443</span><span class="sxs-lookup"><span data-stu-id="87b9f-304">443</span></span>  <br/> |<span data-ttu-id="87b9f-305">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="87b9f-305">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="87b9f-306">_tcp을 _sipfederationtls 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-306">_sipfederationtls._tcp.</span></span> <span data-ttu-id="87b9f-307">*domain_name*합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-307">*domain_name*.</span></span> <span data-ttu-id="87b9f-308">예를 들어 fourthcoffee를 _tcp _sipfederationtls 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-308">(for example, _sipfederationtls._tcp.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="87b9f-309">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="87b9f-309">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="87b9f-310">3600</span><span class="sxs-lookup"><span data-stu-id="87b9f-310">3600</span></span>  <br/> |<span data-ttu-id="87b9f-311">SRV</span><span class="sxs-lookup"><span data-stu-id="87b9f-311">SRV</span></span>  <br/> |<span data-ttu-id="87b9f-312">100</span><span class="sxs-lookup"><span data-stu-id="87b9f-312">100</span></span>  <br/> |<span data-ttu-id="87b9f-313">1 </span><span class="sxs-lookup"><span data-stu-id="87b9f-313">1</span></span>  <br/> |<span data-ttu-id="87b9f-314">5061</span><span class="sxs-lookup"><span data-stu-id="87b9f-314">5061</span></span>  <br/> |<span data-ttu-id="87b9f-315">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="87b9f-315">sipfed.online.lync.com</span></span>  <br/> |
   

4. <span data-ttu-id="87b9f-316">**레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-316">Select **Add Record**.</span></span>

  
5. <span data-ttu-id="87b9f-317">다른 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-317">Add the other SRV record.</span></span>
    
    <span data-ttu-id="87b9f-318">**레코드 추가** 구역에서 표의 다음 행 값을 사용 하 여 레코드를 만들고 다시 **레코드 추가** 를 선택 하 여 해당 레코드를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-318">In the **Add a Record** section, create a record by using the values from the next row in the table, and then again select **Add Record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="87b9f-319">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="87b9f-319">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="87b9f-320">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b9f-320">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="87b9f-321">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87b9f-321">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
