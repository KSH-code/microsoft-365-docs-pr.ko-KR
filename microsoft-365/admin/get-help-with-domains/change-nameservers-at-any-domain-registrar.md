---
title: 도메인 등록 기관에서 이름 서버를 변경하여 Office 365 설정
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
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: 전자 메일 및 비즈니스용 Skype 온라인 등의 서비스에서 고유한 도메인 이름을 사용 하도록 Office 365에서 도메인을 추가 및 설정 하는 방법에 대해 알아봅니다.
ms.custom: okr_smb
ms.openlocfilehash: 3030fc33a6d528fd6cb4e97c27cdbb7c251e9a97
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255155"
---
# <a name="change-nameservers-to-set-up-office-365-with-any-domain-registrar"></a><span data-ttu-id="23773-103">도메인 등록 기관에서 이름 서버를 변경하여 Office 365 설정</span><span class="sxs-lookup"><span data-stu-id="23773-103">Change nameservers to set up Office 365 with any domain registrar</span></span>

 <span data-ttu-id="23773-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="23773-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="23773-105">먼저 [도메인 설정 (호스트 관련 지침)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) 을 선택 하 여 등록 기관에 대 한 지침이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="23773-105">Check [Set up your domain (host-specific instructions)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) first to see if we have instructions for your registrar.</span></span> 
  
<span data-ttu-id="23773-106">다음 지침에 따라 Office 365에서 도메인을 추가 및 설정 하 여 전자 메일 및 비즈니스용 Skype Online과 같은 서비스에서 자체 도메인 이름을 사용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="23773-106">Follow these instructions to add and set up your domain in Office 365 so your services like email and Skype for Business Online will use your own domain name.</span></span> <span data-ttu-id="23773-107">이렇게 하려면 도메인을 확인 한 다음 올바른 DNS 레코드를 설정할 수 있도록 도메인의 이름 서버를 Office 365으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="23773-107">To do this, you'll verify your domain, and then change your domain's nameservers to Office 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="23773-108">다음 문이 상황을 설명 하는 경우 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="23773-108">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="23773-109">사용자의 고유한 도메인을 Office 365와 연동되도록 설정하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="23773-109">You have your own domain and want to set it up to work with Office 365.</span></span>
    
- <span data-ttu-id="23773-p102">Office 365를 사용하여 DNS 레코드를 관리하고 싶습니다. 원하는 경우 [고유한 DNS 레코드를 관리](../setup/add-domain.md)할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23773-p102">You want Office 365 to manage your DNS records for you. (If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="23773-112">확인을 위해 TXT 또는 MX 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="23773-112">Add a TXT or MX record for verification</span></span>
<span data-ttu-id="23773-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="23773-113"><a name="BKMK_verify"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="23773-p103">이러한 레코드 중 하나만 만들어집니다. TXT가 기본 레코드 형식이지만 일부 DNS 호스팅 공급자는 이를 지원하지 않으며, 이 경우 대신 MX 레코드를 만들면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23773-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="23773-p104">Office 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Office 365에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23773-p104">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="23773-p105">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23773-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="23773-120">DNS 호스팅 공급자 웹 사이트에서 새 레코드를 만들 수 있는 영역을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="23773-120">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="23773-121">DNS 호스팅 공급자의 웹 사이트에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="23773-121">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="23773-122">도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="23773-122">Choose your domain.</span></span>
    
3. <span data-ttu-id="23773-123">도메인의 DNS 레코드를 편집할 수 있는 페이지를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="23773-123">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="23773-124">레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="23773-124">Create the record</span></span>

<span data-ttu-id="23773-125">만드는 레코드가 TXT 레코드인지 MX 레코드인지에 따라 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="23773-125">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="23773-126">**TXT 레코드를 만드는 경우 다음 값을 사용합니다.**</span><span class="sxs-lookup"><span data-stu-id="23773-126">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="23773-127">**Record Type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="23773-127">**Record Type**</span></span> <br/> |<span data-ttu-id="23773-128">**Alias(별칭)** 또는 **Host Name(호스트 이름)**</span><span class="sxs-lookup"><span data-stu-id="23773-128">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="23773-129">**Value(값)**</span><span class="sxs-lookup"><span data-stu-id="23773-129">**Value**</span></span> <br/> |<span data-ttu-id="23773-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="23773-130">**TTL**</span></span> <br/> |
|<span data-ttu-id="23773-131">TXT</span><span class="sxs-lookup"><span data-stu-id="23773-131">TXT</span></span>  <br/> |<span data-ttu-id="23773-132">다음 중 하나를 수행합니다. **@** 을 입력하거나 필드를 비워 두거나 도메인 이름을 입력합니다.    </span><span class="sxs-lookup"><span data-stu-id="23773-132">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="23773-133">> [!NOTE]> 이 필드의 경우 각 DNS 호스트마다 요구 사항이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="23773-133">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="23773-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="23773-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="23773-p106">> [!NOTE]> 이 값은 예시입니다. 여기에는 Office 365의 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.           [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="23773-p106">> [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="23773-138">이 값을 **1시간** 또는 등가의 분( **60** ), 초( **3600** ) 단위로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="23773-138">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="23773-139">**MX 레코드를 만드는 경우 다음 값을 사용합니다.**</span><span class="sxs-lookup"><span data-stu-id="23773-139">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="23773-140">**Record Type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="23773-140">**Record Type**</span></span>|<span data-ttu-id="23773-141">**Alias(별칭)** 또는 **Host Name(호스트 이름)**</span><span class="sxs-lookup"><span data-stu-id="23773-141">**Alias** or **Host Name**</span></span>|<span data-ttu-id="23773-142">**Value(값)**</span><span class="sxs-lookup"><span data-stu-id="23773-142">**Value**</span></span>|<span data-ttu-id="23773-143">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="23773-143">**Priority**</span></span>|<span data-ttu-id="23773-144">**TTL**</span><span class="sxs-lookup"><span data-stu-id="23773-144">**TTL**</span></span>|
|<span data-ttu-id="23773-145">MX</span><span class="sxs-lookup"><span data-stu-id="23773-145">MX</span></span>|<span data-ttu-id="23773-146">**@** 또는 도메인 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="23773-146">Type either **@** or your domain name.</span></span> |<span data-ttu-id="23773-p107">MS=ms *XXXXXXXX* > [!NOTE]> 이 값은 예시입니다. 여기에는 Office 365의 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.           [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="23773-p107">MS=ms *XXXXXXXX* > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="23773-150">**우선 순위**에 대해 메일 흐름에 사용 되는 MX 레코드와의 충돌을 방지 하기 위해 기존 MX 레코드의 우선 순위 보다 낮은 우선 순위를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="23773-150">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="23773-151">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](../setup/domains-faq.md#what-is-mx-priority)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="23773-151">For more information about priority, see [What is MX priority?](../setup/domains-faq.md#what-is-mx-priority)</span></span> |<span data-ttu-id="23773-152">이 값을 **1시간** 또는 등가의 분( **60** ), 초( **3600** ) 단위로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="23773-152">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="23773-153">레코드 저장</span><span class="sxs-lookup"><span data-stu-id="23773-153">Save the record</span></span>

<span data-ttu-id="23773-154">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="23773-154">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="23773-155">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="23773-155">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="23773-156">관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="23773-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="23773-157">**도메인** 페이지에서 확인 하려는 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="23773-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="23773-158">**설정** 페이지에서 **설정 시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="23773-158">On the **Setup** page, select **Start setup**.</span></span>
 
    
  
4. <span data-ttu-id="23773-159">**도메인 확인** 페이지에서 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="23773-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="23773-p109">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="23773-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="23773-163">도메인의 NS(이름 서버) 레코드 변경</span><span class="sxs-lookup"><span data-stu-id="23773-163">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="23773-164"><a name="BKMK_nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="23773-164"><a name="BKMK_nameservers"> </a></span></span>

<span data-ttu-id="23773-p110">Office 365의 도메인 설정 마법사의 마지막 단계에서는 한 개의 작업을 수행합니다. 전자 메일 같은 Office 365서비스에 도메인을 설정하려면 도메인 등록 기관에서 도메인의 이름 서버(또는 NS) 레코드를 변경하여 Office 365 기본 및 보조 이름 서버를 가리키도록 합니다. Office 365에서 DNS를 호스팅하므로 서비스를 위한 필수 DNS 레코드가 자동으로 설정됩니다. 도메인 등록 기관의 웹 사이트에서 도움말 콘텐츠를 제공한 경우 해당 단계를 따라 이름 서버 레코드를 직접 업데이트할 수 있습니다. DNS에 익숙하지 않다면 도메인 등록 기관의 지원에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="23773-p110">When you get to the last step of the domains setup wizard in Office 365, you have one task remaining. To set up your domain with Office 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Office 365 primary and secondary nameservers. Then, because Office 365 hosts your DNS, the required DNS records for your services are set up automatically for you. You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website. If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="23773-170">도메인 등록 기관 웹 사이트에서 도메인 이름 서버를 직접 변경하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="23773-170">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="23773-171">도메인 등록 기관의 웹 사이트에서 도메인의 이름 서버를 편집할 수 있는 영역을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="23773-171">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="23773-172">이름 서버 레코드를 두 개 만들거나 기존 이름 서버 레코드를 다음 값과 일치하도록 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="23773-172">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="23773-173">첫 번째 이름 서버</span><span class="sxs-lookup"><span data-stu-id="23773-173">First nameserver</span></span>  <br/> |<span data-ttu-id="23773-174">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="23773-174">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="23773-175">두 번째 이름 서버</span><span class="sxs-lookup"><span data-stu-id="23773-175">Second nameserver</span></span>  <br/> |<span data-ttu-id="23773-176">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="23773-176">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="23773-177">두 개 이상의 이름 서버 레코드를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23773-177">You should use at least two nameserver records.</span></span> <span data-ttu-id="23773-178">나열 된 다른 이름 서버 있으면 삭제 하거나 **ns3.bdm.microsoftonline.com** 및 **ns4.bdm.microsoftonline.com**로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23773-178">If there are any other nameservers listed, you can either delete them, or change them to **ns3.bdm.microsoftonline.com** and **ns4.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="23773-179">변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="23773-179">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="23773-p112">Office 365 이름 서버를 가리키도록 도메인의 NS 레코드를 변경하면 현재 도메인에 연결되는 모든 서비스가 영향을 받습니다. 전자 메일 주소 추가와 같은 마법사의 특정 단계를 건너뛰거나 블로그, 장바구니 또는 기타 서비스에 사용자 도메인을 사용 중인 경우 추가 단계가 필요합니다. 추가 단계를 수행하지 않으면 이러한 변경으로 인해 전자 메일 또는 현재 웹 사이트에 액세스 불가와 같은 서비스 중단이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23773-p112">When you change your domain's NS records to point to the Office 365 nameservers, all the services that are currently associated with your domain are affected. If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required. Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="23773-183">도메인 등록 기관의 웹 사이트에서 도메인의 이름 서버를 편집할 수 있는 영역을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="23773-183">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="23773-184">이름 서버 레코드를 두 개 만들거나 기존 이름 서버 레코드를 다음 값과 일치하도록 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="23773-184">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="23773-185">첫 번째 이름 서버</span><span class="sxs-lookup"><span data-stu-id="23773-185">First nameserver</span></span>  <br/> |<span data-ttu-id="23773-186">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="23773-186">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="23773-187">두 번째 이름 서버</span><span class="sxs-lookup"><span data-stu-id="23773-187">Second nameserver</span></span>  <br/> |<span data-ttu-id="23773-188">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="23773-188">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="23773-189">두 개 이상의 이름 서버 레코드를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23773-189">You should use at least two nameserver records.</span></span> <span data-ttu-id="23773-190">나열 된 다른 이름 서버 있으면 삭제 하거나 **ns3.dns.partner.microsoftonline.cn** 및 **ns4.dns.partner.microsoftonline.cn**로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23773-190">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="23773-191">변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="23773-191">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="23773-192">21Vianet 이름 서버에서 운영 하는 Office 365을 가리키도록 도메인의 NS 레코드를 변경 하면 현재 도메인에 연결 된 모든 서비스가 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="23773-192">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="23773-193">전자 메일 주소 추가와 같은 마법사의 특정 단계를 건너뛰거나 블로그, 장바구니 또는 기타 서비스에 사용자 도메인을 사용 중인 경우 추가 단계가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="23773-193">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="23773-194">추가 단계를 수행하지 않으면 이러한 변경으로 인해 전자 메일 또는 현재 웹 사이트에 액세스 불가와 같은 서비스 중단이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23773-194">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="23773-195">예를 들어, 전자 메일 및 웹 사이트 호스팅 시 다음과 같은 추가 단계가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="23773-195">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="23773-196">이름 서버 레코드를 변경하기 전에 사용자 도메인을 사용하는 모든 전자 메일 주소를 Office 365로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="23773-196">Move all email addresses that use your domain to Office 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="23773-197">현재 웹 사이트 주소에 사용되는 도메인(예: www.fourthcoffee.com)을 추가하려면, 도메인을 추가하는 동안 현재 사이트가 호스팅되는 곳에 웹 사이트가 호스팅되도록 하는 단계를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23773-197">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="23773-198">Office 365을 가리키도록 도메인의 NS 레코드를 변경한 후에도 사용자가 여전히 웹 사이트로 이동할 수 있도록 사이트를 호스트 하는 웹 사이트를 유지 하기 위해 도메인을 추가 하는 동안 단계를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23773-198">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Office 365.</span></span>

1. <span data-ttu-id="23773-199">관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="23773-199">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

3. <span data-ttu-id="23773-200">도메인 페이지에서 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="23773-200">On the Domains page, select a domain.</span></span>

4. <span data-ttu-id="23773-201">**DNS 설정**에서 **사용자 지정 레코드**를 선택한 다음 **새 사용자 지정 레코드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="23773-201">Under **DNS settings**, select **Custom Records**, and then choose **New custom record**.</span></span>

5. <span data-ttu-id="23773-202">추가할 DNS 레코드 유형을 선택 하 고 새 레코드에 대 한 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="23773-202">Select the type of DNS record you want to add, and type the information for the new record.</span></span>

6. <span data-ttu-id="23773-203">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="23773-203">Select **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="23773-p116">이름 서버 레코드 업데이트가 인터넷의 DNS 시스템 전체에 업데이트되기까지 몇 시간이 걸릴 수 있습니다. 그 후에는 Office 365 전자 메일 및 기타 서비스가 모두 사용자의 도메인을 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="23773-p116">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  

