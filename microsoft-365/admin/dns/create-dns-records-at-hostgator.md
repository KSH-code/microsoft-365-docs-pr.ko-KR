---
title: Hostgator에서 Office 365용 DNS 레코드 만들기
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대 한 DNS 레코드를 Office 365 용 Hostgator에 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: cb0b26081e5946ed2558d090c976847197ed7eb8
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42249143"
---
# <a name="create-dns-records-at-hostgator-for-office-365"></a><span data-ttu-id="d346b-103">Hostgator에서 Office 365용 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="d346b-103">Create DNS records at Hostgator for Office 365</span></span>

 <span data-ttu-id="d346b-104">**원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="d346b-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="d346b-105">DNS 호스팅 공급자로 Hostgator를 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-105">If Hostgator is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d346b-106">이 문서의 다른 절차를 사용 하 여 DNS 레코드를 추가 하기 전에 첫 번째 procedurebelow를 수행 하 여 [호스팅 계정에 대 한 도메인을 가리키도록](#point-your-domain-to-your-hosting-account)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-106">You must perform the first procedurebelow, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account), before you add DNS records by using any of the other procedures in this article.</span></span> 

<span data-ttu-id="d346b-107">Hostgator에서 이렇게 변경하고 나면 도메인이 Office 365 서비스에서 작동하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-107">After you make all of these changes at Hostgator, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="d346b-108">Office 365에서 웹 사이트의 웹 호스팅 및 DNS에 대한 자세한 내용은 [Office 365에서 공개 웹 사이트 사용](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d346b-108">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d346b-109">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="d346b-109">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="d346b-110">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="d346b-110">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="d346b-111">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제에 문제가 있는 경우 [Office 365에서 도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d346b-111">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="point-your-domain-to-your-hosting-account"></a><span data-ttu-id="d346b-112">도메인을 호스팅 계정에 연결</span><span class="sxs-lookup"><span data-stu-id="d346b-112">Point your domain to your hosting account</span></span>
<span data-ttu-id="d346b-113"><a name="BKMK_PointDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="d346b-113"><a name="BKMK_PointDomain"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d346b-114">이 문서의 다른 절차를 수행하기 전에 이 절차를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-114">You must perform this procedure before you perform any of the other procedures in this article.</span></span> 
  
<span data-ttu-id="d346b-115">이러한 단계에 따라 도메인 및 호스팅 계정을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-115">Follow these steps to associate your domain and hosting accounts.</span></span>
  
1. <span data-ttu-id="d346b-p102">시작하려면 [이 링크](https://portal.hostgator.com/)를 사용하여 Hostgator의 도메인 관리 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-p102">To get started, go to your domain management page at Hostgator by using [this link](https://portal.hostgator.com/). You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="d346b-118">왼쪽에서 **도메인** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-118">Select **Domains** on the left.</span></span>
  
3. <span data-ttu-id="d346b-119">**도메인 관리** 페이지에서 업데이트 하려는 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-119">On the **Manage Domains** page, select the domain you want to update.</span></span> 
  
4. <span data-ttu-id="d346b-120">왼쪽의 팝업 메뉴에서 **이름 서버**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-120">On the pop-out menu on the left, select **Name Servers**.</span></span>
  
5. <span data-ttu-id="d346b-121">도메인의 **이름 서버** 페이지에 있는 **이 도메인을 내 호스팅 계정으로 자동 가리키기** 드롭다운 목록에서 도메인과 연결 된 호스팅 계정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-121">On the **Name Servers** page for your domain, in the **Automatically point this domain to my hosting account** drop-down list, choose the hosting account that is associated with your domain.</span></span> 
  
6. <span data-ttu-id="d346b-122">**이름 서버 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-122">Select **Save Name Servers**.</span></span>
    
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="d346b-123">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="d346b-123">Add a TXT record for verification</span></span>
<span data-ttu-id="d346b-124"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="d346b-124"><a name="BKMK_verify"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d346b-125">이 절차를 수행하기 전에 이 문서의 첫 번째 구역에 있는 절차, [도메인을 호스팅 계정에 연결](#point-your-domain-to-your-hosting-account)을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-125">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
<span data-ttu-id="d346b-p103">Office 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Office 365에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d346b-p104">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="d346b-130">To get started, go to your cPanel page at Hostgator.</span><span class="sxs-lookup"><span data-stu-id="d346b-130">To get started, go to your cPanel page at Hostgator.</span></span> <span data-ttu-id="d346b-131">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="d346b-131">You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="d346b-132">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="d346b-132">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="d346b-133">cPanel 주소의 형식은 https://YourSiteAddress:secure-port-number와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-133">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="d346b-134">Hostgator에서 받은 등록 전자 메일에는 해당 주소가 지정 되 고, **호스팅** 페이지 에서도 cpanel 링크를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-134">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d346b-p107">도메인과 연결된 cPanel을 소유하려면 Hostgator의 호스팅 계정이 필요합니다. Office 365를 시작하려면 Hostgator에서 호스팅 계정을 구입하거나 [이름 서버가 Office 365를 가리키도록 다시 위임](change-nameservers-at-hostgator.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-p107">To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started with Office 365, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Office 365](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="d346b-137">**제어판** 페이지의 **도메인** 영역에서 **고급 영역 편집기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-137">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="d346b-138">**고급 영역 편집기** 페이지의 **레코드 추가** 영역에서 새 레코드 용 상자에 다음 표의 값을 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-138">On the **Advanced Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d346b-139">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="d346b-139">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d346b-140">**이름**</span><span class="sxs-lookup"><span data-stu-id="d346b-140">**Name**</span></span> <br/> |<span data-ttu-id="d346b-141">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d346b-141">**TTL**</span></span> <br/> |<span data-ttu-id="d346b-142">**유형**</span><span class="sxs-lookup"><span data-stu-id="d346b-142">**Type**</span></span> <br/> |<span data-ttu-id="d346b-143">**TXT 데이터**</span><span class="sxs-lookup"><span data-stu-id="d346b-143">**TXT Data**</span></span> <br/> |
    |<span data-ttu-id="d346b-144">*Domain_name*를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-144">Use your  *domain_name*.</span></span> <span data-ttu-id="d346b-145">(for example, fourthcoffee.com.)</span><span class="sxs-lookup"><span data-stu-id="d346b-145">(for example, fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="d346b-146">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="d346b-146">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d346b-147">개</span><span class="sxs-lookup"><span data-stu-id="d346b-147">1</span></span>  <br/> |<span data-ttu-id="d346b-148">TXT</span><span class="sxs-lookup"><span data-stu-id="d346b-148">TXT</span></span>  <br/> |<span data-ttu-id="d346b-149">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="d346b-149">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="d346b-150">**참고:** 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-150">**Note:** This is an example.</span></span> <span data-ttu-id="d346b-151">여기에는 Office 365의 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-151">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="d346b-152">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="d346b-152">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="d346b-153">**레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-153">Select **Add Record**.</span></span>
    
5. <span data-ttu-id="d346b-154">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-154">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="d346b-155">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="d346b-155">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="d346b-156">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="d346b-156">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="d346b-157">관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="d346b-158">**도메인** 페이지에서 확인 하려는 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-158">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="d346b-159">**설정** 페이지에서 **설정 시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-159">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="d346b-160">**도메인 확인** 페이지에서 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-160">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d346b-161">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="d346b-161">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="d346b-162">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="d346b-162">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="d346b-163">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제에 문제가 있는 경우 [Office 365에서 도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d346b-163">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="d346b-164">사용자 도메인의 전자 메일이 Office 365로 전송되도록 MX 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="d346b-164">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="d346b-165"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="d346b-165"><a name="BKMK_add_MX"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d346b-166">이 절차를 수행하기 전에 이 문서의 첫 번째 구역에 있는 절차, [도메인을 호스팅 계정에 연결](#point-your-domain-to-your-hosting-account)을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-166">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="d346b-p111">시작하려면 Hostgator의 cPanel 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-p111">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="d346b-169">(Hostgator에서 호스팅되는 각 계정에는 고유 cPanel 주소가 할당되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-169">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="d346b-170">cPanel 주소의 형식은 https://YourSiteAddress:secure-port-number와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-170">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="d346b-171">Hostgator에서 받은 등록 전자 메일에는 해당 주소가 지정 되 고, **호스팅** 페이지 에서도 cpanel 링크를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-171">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d346b-p113">도메인과 연결된 cPanel을 소유하려면 Hostgator의 호스팅 계정이 필요합니다. Office 365를 시작하려면 Hostgator에서 호스팅 계정을 구입하거나 [이름 서버가 Office 365를 가리키도록 다시 위임](change-nameservers-at-hostgator.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-p113">To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started with Office 365, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Office 365](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="d346b-174">**제어판** 페이지의 **전자 메일** 영역에서 **MX 항목**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-174">On the **Control Panel** page, in the **Email** area, select **MX Entry**.</span></span>
    
 
3. <span data-ttu-id="d346b-175">**전자 메일 라우팅** 영역에서 **원격 메일 교환기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-175">In the **Email Routing** area, select **Remote Mail Exchanger**.</span></span>

4. <span data-ttu-id="d346b-176">**변경을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-176">Select **Change**.</span></span>
  
5. <span data-ttu-id="d346b-177">**새 레코드 추가** 영역의 새 레코드 용 상자에 다음 표의 값을 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-177">In the **Add a New Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="d346b-178">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="d346b-178">**Priority**</span></span>|<span data-ttu-id="d346b-179">**대상**</span><span class="sxs-lookup"><span data-stu-id="d346b-179">**Destination**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="d346b-180">개</span><span class="sxs-lookup"><span data-stu-id="d346b-180">0</span></span>  <br/> <span data-ttu-id="d346b-181">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d346b-181">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="d346b-182">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d346b-182">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="d346b-183">**참고:** \< Office 365 계정에서 *도메인 키* \> 를 가져옵니다.  </span><span class="sxs-lookup"><span data-stu-id="d346b-183">**Note:** Get your \< *domain-key*  \> from your Office 365 account.</span></span>  [<span data-ttu-id="d346b-184">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="d346b-184">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
  
6. <span data-ttu-id="d346b-185">**새 레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-185">Select **Add New Record**.</span></span>
   
 
7. <span data-ttu-id="d346b-186">**Mx 레코드** 구역에 다른 mx 레코드가 있으면 각 레코드를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-186">If there are any other MX records in the **MX Records** section, remove each of them.</span></span> 

    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="d346b-187">Office 365에 필요한 6개의 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="d346b-187">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="d346b-188"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="d346b-188"><a name="BKMK_add_CNAME"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d346b-189">이 절차를 수행하기 전에 이 문서의 첫 번째 구역에 있는 절차, [도메인을 호스팅 계정에 연결](#point-your-domain-to-your-hosting-account)을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-189">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="d346b-p115">시작하려면 Hostgator의 cPanel 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-p115">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="d346b-192">(Hostgator에서 호스팅되는 각 계정에는 고유 cPanel 주소가 할당되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-192">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="d346b-193">cPanel 주소의 형식은 https://YourSiteAddress:secure-port-number와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-193">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="d346b-194">Hostgator에서 받은 등록 전자 메일에는 해당 주소가 지정 되 고, **호스팅** 페이지 에서도 cpanel 링크를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-194">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d346b-p117">도메인과 연결된 cPanel을 소유하려면 Hostgator의 호스팅 계정이 필요합니다. Office 365를 시작하려면 Hostgator에서 호스팅 계정을 구입하거나 [이름 서버가 Office 365를 가리키도록 다시 위임](change-nameservers-at-hostgator.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-p117">To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started with Office 365, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Office 365](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="d346b-197">**제어판** 페이지의 **도메인** 영역에서 **고급 영역 편집기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-197">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="d346b-198">6개의 CNAME 레코드 중 첫 번째 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-198">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="d346b-199">**고급 영역 편집기** 페이지의 **레코드 추가** 영역의 새 레코드 용 상자에 다음 표에 있는 첫 번째 행의 값을 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-199">On the **Advanced Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="d346b-200">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="d346b-200">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="d346b-201">**이름**</span><span class="sxs-lookup"><span data-stu-id="d346b-201">**Name**</span></span>|<span data-ttu-id="d346b-202">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d346b-202">**TTL**</span></span>|<span data-ttu-id="d346b-203">**종류**</span><span class="sxs-lookup"><span data-stu-id="d346b-203">**Type**</span></span>|<span data-ttu-id="d346b-204">**CNAME**</span><span class="sxs-lookup"><span data-stu-id="d346b-204">**CNAME**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d346b-205">autodiscover.</span><span class="sxs-lookup"><span data-stu-id="d346b-205">autodiscover.</span></span> <span data-ttu-id="d346b-206">*domain_name*합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-206">*domain_name*.</span></span> <span data-ttu-id="d346b-207">(예: autodiscover.fourthcoffee.com)</span><span class="sxs-lookup"><span data-stu-id="d346b-207">(for example, autodiscover.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="d346b-208">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="d346b-208">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d346b-209">3600</span><span class="sxs-lookup"><span data-stu-id="d346b-209">3600</span></span>  <br/> |<span data-ttu-id="d346b-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="d346b-210">CNAME</span></span>  <br/> |<span data-ttu-id="d346b-211">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d346b-211">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="d346b-212">sip.</span><span class="sxs-lookup"><span data-stu-id="d346b-212">sip.</span></span> <span data-ttu-id="d346b-213">*domain_name*합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-213">*domain_name*.</span></span> <span data-ttu-id="d346b-214">(예: sip.fourthcoffee.com)</span><span class="sxs-lookup"><span data-stu-id="d346b-214">(for example, sip.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="d346b-215">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="d346b-215">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d346b-216">3600</span><span class="sxs-lookup"><span data-stu-id="d346b-216">3600</span></span>  <br/> |<span data-ttu-id="d346b-217">CNAME</span><span class="sxs-lookup"><span data-stu-id="d346b-217">CNAME</span></span>  <br/> |<span data-ttu-id="d346b-218">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d346b-218">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d346b-219">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="d346b-219">lyncdiscover.</span></span> <span data-ttu-id="d346b-220">*domain_name*합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-220">*domain_name*.</span></span> <span data-ttu-id="d346b-221">(예: lyncdiscover.fourthcoffee.com)</span><span class="sxs-lookup"><span data-stu-id="d346b-221">(for example, lyncdiscover.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="d346b-222">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="d346b-222">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d346b-223">3600</span><span class="sxs-lookup"><span data-stu-id="d346b-223">3600</span></span>  <br/> |<span data-ttu-id="d346b-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="d346b-224">CNAME</span></span>  <br/> |<span data-ttu-id="d346b-225">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d346b-225">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d346b-226">enterpriseregistration.</span><span class="sxs-lookup"><span data-stu-id="d346b-226">enterpriseregistration.</span></span> <span data-ttu-id="d346b-227">*domain_name*합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-227">*domain_name*.</span></span> <span data-ttu-id="d346b-228">(예: enterpriseregistration.fourthcoffee.com)</span><span class="sxs-lookup"><span data-stu-id="d346b-228">(for example, enterpriseregistration.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="d346b-229">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="d346b-229">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d346b-230">3600</span><span class="sxs-lookup"><span data-stu-id="d346b-230">3600</span></span>  <br/> |<span data-ttu-id="d346b-231">CNAME</span><span class="sxs-lookup"><span data-stu-id="d346b-231">CNAME</span></span>  <br/> |<span data-ttu-id="d346b-232">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="d346b-232">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="d346b-233">enterpriseenrollment.</span><span class="sxs-lookup"><span data-stu-id="d346b-233">enterpriseenrollment.</span></span> <span data-ttu-id="d346b-234">*domain_name*합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-234">*domain_name*.</span></span> <span data-ttu-id="d346b-235">(예: enterpriseregistration.fourthcoffee.com)</span><span class="sxs-lookup"><span data-stu-id="d346b-235">(for example, enterpriseregistration.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="d346b-236">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="d346b-236">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d346b-237">3600</span><span class="sxs-lookup"><span data-stu-id="d346b-237">3600</span></span>  <br/> |<span data-ttu-id="d346b-238">CNAME</span><span class="sxs-lookup"><span data-stu-id="d346b-238">CNAME</span></span>  <br/> |<span data-ttu-id="d346b-239">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d346b-239">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |

  
4. <span data-ttu-id="d346b-240">**레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-240">Select **Add Record**.</span></span>

5. <span data-ttu-id="d346b-241">나머지 5개의 CNAME 레코드를 각각 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-241">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="d346b-242">**레코드 추가** 구역에서 표의 다음 행 값을 사용 하 여 레코드를 만들고 다시 **레코드 추가** 를 선택 하 여 해당 레코드를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-242">In the **Add a Record** section, create a record by using the values from the next row in the table, and then again select **Add Record** to complete that record.</span></span> 
    
    <span data-ttu-id="d346b-243">6개의 CNAME 레코드를 모두 만들 때까지 이 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-243">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="d346b-244">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="d346b-244">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="d346b-245"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="d346b-245"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d346b-246">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="d346b-246">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="d346b-247">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="d346b-247">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="d346b-248">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="d346b-248">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="d346b-249">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="d346b-249">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="d346b-250">Need examples?</span><span class="sxs-lookup"><span data-stu-id="d346b-250">Need examples?</span></span> <span data-ttu-id="d346b-251">이러한 [외부 도메인 이름 시스템 레코드에서 Office 365를](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords)확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="d346b-251">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="d346b-252">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="d346b-252">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="d346b-253">이 절차를 수행하기 전에 이 문서의 첫 번째 구역에 있는 절차, [도메인을 호스팅 계정에 연결](#point-your-domain-to-your-hosting-account)을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-253">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="d346b-p124">시작하려면 Hostgator의 cPanel 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-p124">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="d346b-256">(Hostgator에서 호스팅되는 각 계정에는 고유 cPanel 주소가 할당되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-256">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="d346b-257">cPanel 주소의 형식은 https://YourSiteAddress:secure-port-number와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-257">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="d346b-258">Hostgator에서 받은 등록 전자 메일에는 해당 주소가 지정 되 고, **호스팅** 페이지 에서도 cpanel 링크를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-258">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d346b-p126">도메인과 연결된 cPanel을 소유하려면 Hostgator의 호스팅 계정이 필요합니다. Office 365를 시작하려면 Hostgator에서 호스팅 계정을 구입하거나 [이름 서버가 Office 365를 가리키도록 다시 위임](change-nameservers-at-hostgator.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-p126">To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started with Office 365, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Office 365](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="d346b-261">**제어판** 페이지의 **도메인** 영역에서 **고급 영역 편집기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-261">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="d346b-262">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d346b-262">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d346b-263">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="d346b-263">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="d346b-264">**이름**</span><span class="sxs-lookup"><span data-stu-id="d346b-264">**Name**</span></span>|<span data-ttu-id="d346b-265">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d346b-265">**TTL**</span></span>|<span data-ttu-id="d346b-266">**유형**</span><span class="sxs-lookup"><span data-stu-id="d346b-266">**Type**</span></span>|<span data-ttu-id="d346b-267">**TXT 데이터**</span><span class="sxs-lookup"><span data-stu-id="d346b-267">**TXT Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d346b-268">*Domain_name*를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-268">Use your  *domain_name*.</span></span> <span data-ttu-id="d346b-269">(for example, fourthcoffee.com.)</span><span class="sxs-lookup"><span data-stu-id="d346b-269">(for example, fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="d346b-270">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="d346b-270">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d346b-271">3600</span><span class="sxs-lookup"><span data-stu-id="d346b-271">3600</span></span>  <br/> |<span data-ttu-id="d346b-272">TXT</span><span class="sxs-lookup"><span data-stu-id="d346b-272">TXT</span></span>  <br/> |<span data-ttu-id="d346b-273">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="d346b-273">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="d346b-274">**참고:** 모든 공백이 올바르게 유지 되도록이 항목을 복사 하 여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-274">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
  
4. <span data-ttu-id="d346b-275">**레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-275">Select **Add Record**.</span></span>
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="d346b-276">Office 365에 필요한 2개의 SRV 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="d346b-276">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="d346b-277"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="d346b-277"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d346b-278">이 절차를 수행하기 전에 이 문서의 첫 번째 구역에 있는 절차, [도메인을 호스팅 계정에 연결](#point-your-domain-to-your-hosting-account)을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-278">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="d346b-p128">시작하려면 Hostgator의 cPanel 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-p128">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="d346b-281">(Hostgator에서 호스팅되는 각 계정에는 고유 cPanel 주소가 할당되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-281">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="d346b-282">cPanel 주소의 형식은 https://YourSiteAddress:secure-port-number와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-282">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="d346b-283">Hostgator에서 받은 등록 전자 메일에는 해당 주소가 지정 되 고, **호스팅** 페이지 에서도 cpanel 링크를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-283">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d346b-p130">도메인과 연결된 cPanel을 소유하려면 Hostgator의 호스팅 계정이 필요합니다. Office 365를 시작하려면 Hostgator에서 호스팅 계정을 구입하거나 [이름 서버가 Office 365를 가리키도록 다시 위임](change-nameservers-at-hostgator.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-p130">To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started with Office 365, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Office 365](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="d346b-286">**제어판** 페이지의 **도메인** 영역에서 **고급 영역 편집기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-286">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>

    
3. <span data-ttu-id="d346b-287">2개의 SRV 레코드 중 첫 번째 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-287">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="d346b-288">**고급 DNS 영역 편집기** 페이지의 **레코드 추가** 영역에서 새 레코드용 상자에 다음 표의 첫 번째 행 값을 입력하거나 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-288">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="d346b-289">(드롭다운 목록에서 **Type(종류)** 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="d346b-289">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="d346b-290">**이름**</span><span class="sxs-lookup"><span data-stu-id="d346b-290">**Name**</span></span>|<span data-ttu-id="d346b-291">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d346b-291">**TTL**</span></span>|<span data-ttu-id="d346b-292">**종류**</span><span class="sxs-lookup"><span data-stu-id="d346b-292">**Type**</span></span>|<span data-ttu-id="d346b-293">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="d346b-293">**Priority**</span></span>|<span data-ttu-id="d346b-294">**가중치**</span><span class="sxs-lookup"><span data-stu-id="d346b-294">**Weight**</span></span>|<span data-ttu-id="d346b-295">**포트**</span><span class="sxs-lookup"><span data-stu-id="d346b-295">**Port**</span></span>|<span data-ttu-id="d346b-296">**대상**</span><span class="sxs-lookup"><span data-stu-id="d346b-296">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d346b-297">_tls을 _sip 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-297">_sip._tls.</span></span> <span data-ttu-id="d346b-298">*domain_name*합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-298">*domain_name*.</span></span> <span data-ttu-id="d346b-299">예를 들어 fourthcoffee를 _tls _sip 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-299">(for example, _sip._tls.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="d346b-300">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="d346b-300">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d346b-301">3600</span><span class="sxs-lookup"><span data-stu-id="d346b-301">3600</span></span>  <br/> |<span data-ttu-id="d346b-302">SRV</span><span class="sxs-lookup"><span data-stu-id="d346b-302">SRV</span></span>  <br/> |<span data-ttu-id="d346b-303">100</span><span class="sxs-lookup"><span data-stu-id="d346b-303">100</span></span>  <br/> |<span data-ttu-id="d346b-304">개</span><span class="sxs-lookup"><span data-stu-id="d346b-304">1</span></span>  <br/> |<span data-ttu-id="d346b-305">443</span><span class="sxs-lookup"><span data-stu-id="d346b-305">443</span></span>  <br/> |<span data-ttu-id="d346b-306">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d346b-306">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d346b-307">_tcp을 _sipfederationtls 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-307">_sipfederationtls._tcp.</span></span> <span data-ttu-id="d346b-308">*domain_name*합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-308">*domain_name*.</span></span> <span data-ttu-id="d346b-309">예를 들어 fourthcoffee를 _tcp _sipfederationtls 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-309">(for example, _sipfederationtls._tcp.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="d346b-310">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="d346b-310">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d346b-311">3600</span><span class="sxs-lookup"><span data-stu-id="d346b-311">3600</span></span>  <br/> |<span data-ttu-id="d346b-312">SRV</span><span class="sxs-lookup"><span data-stu-id="d346b-312">SRV</span></span>  <br/> |<span data-ttu-id="d346b-313">100</span><span class="sxs-lookup"><span data-stu-id="d346b-313">100</span></span>  <br/> |<span data-ttu-id="d346b-314">개</span><span class="sxs-lookup"><span data-stu-id="d346b-314">1</span></span>  <br/> |<span data-ttu-id="d346b-315">5061</span><span class="sxs-lookup"><span data-stu-id="d346b-315">5061</span></span>  <br/> |<span data-ttu-id="d346b-316">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d346b-316">sipfed.online.lync.com</span></span>  <br/> |
   

4. <span data-ttu-id="d346b-317">**레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-317">Select **Add Record**.</span></span>

  
5. <span data-ttu-id="d346b-318">다른 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-318">Add the other SRV record.</span></span>
    
    <span data-ttu-id="d346b-319">**레코드 추가** 구역에서 표의 다음 행 값을 사용 하 여 레코드를 만들고 다시 **레코드 추가** 를 선택 하 여 해당 레코드를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d346b-319">In the **Add a Record** section, create a record by using the values from the next row in the table, and then again select **Add Record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="d346b-320">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="d346b-320">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="d346b-321">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="d346b-321">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="d346b-322">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제에 문제가 있는 경우 [Office 365에서 도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d346b-322">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
