---
title: 도메인 등록 기관에서 이름 Microsoft 365 설정
f1.keywords:
- CSH
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: 전자 메일 및 Microsoft 365 같은 서비스가 자체 도메인 이름을 사용할 수 있도록 비즈니스용 Skype 도메인을 추가하고 설정하는 방법을 학습합니다.
ms.openlocfilehash: 7f1ade6cb3013126fb011fe9232b3b4c2e9a82d4
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683130"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a><span data-ttu-id="f8317-103">도메인 등록 기관에서 이름 Microsoft 365 설정</span><span class="sxs-lookup"><span data-stu-id="f8317-103">Change nameservers to set up Microsoft 365 with any domain registrar</span></span>

 <span data-ttu-id="f8317-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="f8317-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="f8317-105">전자 메일 및 전자 메일과 같은 서비스가 사용자 도메인 이름을 Microsoft 365 도메인을 Teams 지침에 따라 도메인을 추가하고 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="f8317-105">Follow these instructions to add and set up your domain in Microsoft 365 so your services like email and Teams will use your own domain name.</span></span> <span data-ttu-id="f8317-106">이렇게하려면 도메인을 확인한 다음 올바른 DNS 레코드를 설정할 수 있도록 도메인의 Microsoft 365 서버로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-106">To do this, you'll verify your domain, and then change your domain's nameservers to Microsoft 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="f8317-107">다음 명령문이 상황에 대해 설명하는 경우 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-107">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="f8317-108">자체 도메인이 있으며 도메인이 사용자 지정 도메인과 함께 작동할 수 있도록 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f8317-108">You have your own domain and want to set it up to work with Microsoft 365.</span></span>
    
- <span data-ttu-id="f8317-109">DNS Microsoft 365 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-109">You want Microsoft 365 to manage your DNS records for you.</span></span> <span data-ttu-id="f8317-110">원하는 경우 [고유한 DNS 레코드를 관리](../setup/add-domain.md)할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-110">(If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="f8317-111">확인을 위해 TXT 또는 MX 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="f8317-111">Add a TXT or MX record for verification</span></span>

> [!NOTE]
> <span data-ttu-id="f8317-p103">이러한 레코드 중 하나만 만들어집니다. TXT가 기본 레코드 형식이지만 일부 DNS 호스팅 공급자는 이를 지원하지 않으며, 이 경우 대신 MX 레코드를 만들면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="f8317-p104">Microsoft 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft 365에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-p104">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f8317-p105">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="f8317-118">DNS 호스팅 공급자의 웹 사이트에서 새 레코드를 만들 수 있는 영역 찾기</span><span class="sxs-lookup"><span data-stu-id="f8317-118">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="f8317-119">DNS 호스팅 공급자의 웹 사이트에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-119">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="f8317-120">도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-120">Choose your domain.</span></span>
    
3. <span data-ttu-id="f8317-121">도메인의 DNS 레코드를 편집할 수 있는 페이지를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-121">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="f8317-122">레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="f8317-122">Create the record</span></span>

<span data-ttu-id="f8317-123">만드는 레코드가 TXT 레코드인지 MX 레코드인지에 따라 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-123">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="f8317-124">**TXT 레코드를 만드는 경우 다음 값을 사용합니다.**</span><span class="sxs-lookup"><span data-stu-id="f8317-124">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f8317-125">**Record Type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="f8317-125">**Record Type**</span></span> <br/> |<span data-ttu-id="f8317-126">**Alias(별칭)** 또는 **Host Name(호스트 이름)**</span><span class="sxs-lookup"><span data-stu-id="f8317-126">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="f8317-127">**Value(값)**</span><span class="sxs-lookup"><span data-stu-id="f8317-127">**Value**</span></span> <br/> |<span data-ttu-id="f8317-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f8317-128">**TTL**</span></span> <br/> |
|<span data-ttu-id="f8317-129">TXT</span><span class="sxs-lookup"><span data-stu-id="f8317-129">TXT</span></span>  <br/> |<span data-ttu-id="f8317-130">다음 중 하나를 수행합니다. **@** 을 입력하거나 필드를 비워 두거나 도메인 이름을 입력합니다.    </span><span class="sxs-lookup"><span data-stu-id="f8317-130">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="f8317-131">> [!NOTE]> 이 필드의 경우 각 DNS 호스트마다 요구 사항이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-131">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="f8317-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="f8317-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="f8317-133">> [!NOTE]> 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-133">> [!NOTE]> This is an example.</span></span> <span data-ttu-id="f8317-134">여기에는 Microsoft 365의 표에 있는 특정 **주소를 지정할 대상 또는 지점** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-134">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="f8317-135">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="f8317-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="f8317-136">이 값을 **1시간** 또는 등가의 분( **60** ), 초( **3600** ) 단위로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-136">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="f8317-137">**MX 레코드를 만드는 경우 다음 값을 사용합니다.**</span><span class="sxs-lookup"><span data-stu-id="f8317-137">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f8317-138">**Record Type(레코드 종류)**</span><span class="sxs-lookup"><span data-stu-id="f8317-138">**Record Type**</span></span>|<span data-ttu-id="f8317-139">**Alias(별칭)** 또는 **Host Name(호스트 이름)**</span><span class="sxs-lookup"><span data-stu-id="f8317-139">**Alias** or **Host Name**</span></span>|<span data-ttu-id="f8317-140">**Value(값)**</span><span class="sxs-lookup"><span data-stu-id="f8317-140">**Value**</span></span>|<span data-ttu-id="f8317-141">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="f8317-141">**Priority**</span></span>|<span data-ttu-id="f8317-142">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f8317-142">**TTL**</span></span>|
|<span data-ttu-id="f8317-143">MX</span><span class="sxs-lookup"><span data-stu-id="f8317-143">MX</span></span>|<span data-ttu-id="f8317-144">**@** 또는 도메인 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-144">Type either **@** or your domain name.</span></span> |<span data-ttu-id="f8317-145">MS=ms *XXXXXXXX* > [!NOTE]> 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-145">MS=ms *XXXXXXXX* > [!NOTE]> This is an example.</span></span> <span data-ttu-id="f8317-146">여기에는 Microsoft 365의 표에 있는 특정 **주소를 지정할 대상 또는 지점** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-146">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="f8317-147">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="f8317-147">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="f8317-148">**우선 순위** 의 경우, 메일 흐름에 사용되는 MX 레코드와의 충돌을 피하기 위해 기존 MX 레코드의 우선 순위보다 낮은 우선 순위를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-148">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="f8317-149">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](../setup/domains-faq.yml)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8317-149">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> |<span data-ttu-id="f8317-150">이 값을 **1시간** 또는 등가의 분( **60** ), 초( **3600** ) 단위로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-150">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="f8317-151">레코드 저장</span><span class="sxs-lookup"><span data-stu-id="f8317-151">Save the record</span></span>

<span data-ttu-id="f8317-152">이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft 365로 돌아가서 Microsoft 365에 레코드를 찾을 것을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-152">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="f8317-153">Microsoft 365에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-153">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="f8317-154">I관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인</a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="f8317-154">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="f8317-155">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-155">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="f8317-156">**설정** 페이지에서 **설정 시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-156">On the **Setup** page, select **Start setup**.</span></span>
 
  
4. <span data-ttu-id="f8317-157">**도메인 확인** 페이지에서 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-157">On the **Verify domain** page, select **Verify**.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="f8317-p109">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8317-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="f8317-161">도메인의 NS(이름 서버) 레코드 변경</span><span class="sxs-lookup"><span data-stu-id="f8317-161">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="f8317-162">도메인 설정 마법사의 마지막 단계에 Microsoft 365 한 번의 작업이 남습니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-162">When you get to the last step of the domains setup wizard in Microsoft 365, you have one task remaining.</span></span> <span data-ttu-id="f8317-163">전자 메일과 같은 Microsoft 365 도메인을 설정하려면 도메인 등록 기관에서 도메인의 이름server(또는 NS) 레코드가 기본 및 보조 이름 Microsoft 365 있도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-163">To set up your domain with Microsoft 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Microsoft 365 primary and secondary nameservers.</span></span> <span data-ttu-id="f8317-164">그런 다음 Microsoft 365 DNS를 호스트하기 때문에 서비스에 필요한 DNS 레코드가 자동으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-164">Then, because Microsoft 365 hosts your DNS, the required DNS records for your services are set up automatically for you.</span></span> <span data-ttu-id="f8317-165">도메인 등록 기관의 웹 사이트에서 도움말 콘텐츠를 제공한 경우 해당 단계를 따라 이름 서버 레코드를 직접 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-165">You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website.</span></span> <span data-ttu-id="f8317-166">DNS에 익숙하지 않다면 도메인 등록 기관의 지원에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="f8317-166">If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="f8317-167">도메인 등록 기관 웹 사이트에서 도메인 이름 서버를 직접 변경하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-167">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="f8317-168">도메인 등록 기관의 웹 사이트에서 도메인 또는 사용자 지정 이름 서비스를 사용할 수 있는 영역의 이름 서비스를 변경할 수 있는 영역을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-168">Find the area on the domain registrar's website where you can change the nameservers for your domain or an area where you can use custom nameservers.</span></span>
    
2. <span data-ttu-id="f8317-169">이름 서비스 레코드를 만들거나 다음 값과 일치하게 기존 이름 서비스 레코드를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-169">Create nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="f8317-170">첫 번째 이름 서버</span><span class="sxs-lookup"><span data-stu-id="f8317-170">First nameserver</span></span>  <br/> |<span data-ttu-id="f8317-171">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="f8317-171">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="f8317-172">두 번째 이름 서버</span><span class="sxs-lookup"><span data-stu-id="f8317-172">Second nameserver</span></span>  <br/> |<span data-ttu-id="f8317-173">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="f8317-173">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="f8317-174">세 번째 이름 서버</span><span class="sxs-lookup"><span data-stu-id="f8317-174">Third nameserver</span></span>  <br/> |<span data-ttu-id="f8317-175">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="f8317-175">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="f8317-176">네 번째 이름 서버</span><span class="sxs-lookup"><span data-stu-id="f8317-176">Fourth nameserver</span></span>  <br/> |<span data-ttu-id="f8317-177">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="f8317-177">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="f8317-178">4개의 레코드를 모두 추가하는 것이 가장 되지만 등록 기관에서 두 개의 레코드만 지원하는 경우 를 추가하고 ns1.bdm.microsoftonline.com **ns2.bdm.microsoftonline.com.**</span><span class="sxs-lookup"><span data-stu-id="f8317-178">It's best to add all four records, but if your registrar only supports two, add **ns1.bdm.microsoftonline.com** and **ns2.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="f8317-179">변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-179">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="f8317-180">도메인의 NS 레코드가 Microsoft 365 이름 Microsoft 365 변경하면 현재 도메인과 연결된 모든 서비스가 영향을 받는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-180">When you change your domain's NS records to point to the Microsoft 365 nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="f8317-181">전자 메일 주소 추가와 같은 마법사의 특정 단계를 건너뛰거나 블로그, 장바구니 또는 기타 서비스에 사용자 도메인을 사용 중인 경우 추가 단계가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-181">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="f8317-182">추가 단계를 수행하지 않으면 이러한 변경으로 인해 전자 메일 또는 현재 웹 사이트에 액세스 불가와 같은 서비스 중단이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-182">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="f8317-183">도메인 등록 기관의 웹 사이트에서 도메인의 이름 서버를 편집할 수 있는 영역을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-183">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="f8317-184">이름 서버 레코드를 두 개 만들거나 기존 이름 서버 레코드를 다음 값과 일치하도록 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-184">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="f8317-185">첫 번째 이름 서버</span><span class="sxs-lookup"><span data-stu-id="f8317-185">First nameserver</span></span>  <br/> |<span data-ttu-id="f8317-186">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="f8317-186">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="f8317-187">두 번째 이름 서버</span><span class="sxs-lookup"><span data-stu-id="f8317-187">Second nameserver</span></span>  <br/> |<span data-ttu-id="f8317-188">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="f8317-188">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="f8317-189">이름 서비스 레코드를 두 개 이상 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-189">You should use at least two nameserver records.</span></span> <span data-ttu-id="f8317-190">나열된 다른 이름servers가 있는 경우 해당 이름을 삭제하거나 에서 으로 ns3.dns.partner.microsoftonline.cn **ns4.dns.partner.microsoftonline.cn.**</span><span class="sxs-lookup"><span data-stu-id="f8317-190">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="f8317-191">변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-191">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="f8317-192">21Vianet 이름 Office 365 운영하는 도메인을 설정하기 위해 도메인의 NS 레코드를 변경하면 현재 도메인과 연결된 모든 서비스가 영향을 받는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-192">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="f8317-193">전자 메일 주소 추가와 같은 마법사의 특정 단계를 건너뛰거나 블로그, 장바구니 또는 기타 서비스에 사용자 도메인을 사용 중인 경우 추가 단계가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-193">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="f8317-194">추가 단계를 수행하지 않으면 이러한 변경으로 인해 전자 메일 또는 현재 웹 사이트에 액세스 불가와 같은 서비스 중단이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-194">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="f8317-195">예를 들어, 전자 메일 및 웹 사이트 호스팅 시 다음과 같은 추가 단계가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-195">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="f8317-196">NS 레코드를 변경하기 전에 도메인을 Microsoft 365 전자 메일 주소를 모두 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="f8317-196">Move all email addresses that use your domain to Microsoft 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="f8317-197">현재 웹 사이트 주소에 사용되는 도메인(예: www.fourthcoffee.com)을 추가하려면, 도메인을 추가하는 동안 현재 사이트가 호스팅되는 곳에 웹 사이트가 호스팅되도록 하는 단계를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-197">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="f8317-198">도메인을 추가하는 동안 사이트가 호스팅되는 웹 사이트를 계속 호스팅할 수 있도록 도메인을 추가하는 동안 아래 단계를 수행하면 사용자가 해당 웹 사이트를 지정하기 위해 도메인의 NS 레코드를 변경한 후에도 웹 사이트에 계속 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f8317-198">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Microsoft 365.</span></span>

1. <span data-ttu-id="f8317-199">I관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인</a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="f8317-199">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="f8317-200">**도메인** 페이지에서 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-200">On the **Domains** page, select a domain.</span></span>

3. <span data-ttu-id="f8317-201">도메인 세부 정보 페이지에서 DNS 레코드 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-201">On the domain details page, select the **DNS records** tab.</span></span>
 
4. <span data-ttu-id="f8317-202">레코드 **추가 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f8317-202">Select **Add record**.</span></span>

5. <span data-ttu-id="f8317-203">사용자 **지정 DNS 레코드 추가** 창의  유형 드롭다운 목록에서 **A(주소)를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f8317-203">In the **Add a custom DNS record** pane, from the **Type** dropdown list, select **A (Address)**.</span></span>

6. <span data-ttu-id="f8317-204">호스트 **이름 또는 별칭 상자에** 를 **@** 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-204">In the **Host name or Alias** box, type **@**.</span></span>

7. <span data-ttu-id="f8317-205">IP **주소 상자에** 현재 호스트되는 웹 사이트의 고정 IP 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-205">In the **IP Address** box, type the static IP address for the website where it's currently hosted.</span></span> <span data-ttu-id="f8317-206">예: 172.16.140.1.</span><span class="sxs-lookup"><span data-stu-id="f8317-206">For example, 172.16.140.1.</span></span>
    
> [!IMPORTANT]
>  <span data-ttu-id="f8317-207">동적 _IP_ 주소가 아니라 웹 사이트의 고정 _IP_ 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-207">This must be a _static_ IP address for the website, not a _dynamic_ IP address.</span></span> <span data-ttu-id="f8317-208">공개 웹 사이트의 고정 IP 주소를 얻을 수 있는지 확인을 위해 웹 사이트를 호스팅하는 사이트를 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="f8317-208">To make sure you can get a static IP address for your public website, check with the site that hosts your website.</span></span>
   
8. <span data-ttu-id="f8317-209">레코드의 TTL 설정을 변경하려면 **TTL** 드롭다운 목록에서 새 기간을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-209">If you want to change the TTL setting for the record, select a new length of time from the **TTL** dropdown list.</span></span> <span data-ttu-id="f8317-210">그렇지 않은 경우 9단계를 계속 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-210">Otherwise, continue to step 9.</span></span>
    
9. <span data-ttu-id="f8317-211">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-211">Select **Save**.</span></span> 
    
<span data-ttu-id="f8317-212">추가로, 고객이 쉽게 사용자의 웹 사이트를 찾을 수 있도록 CNAME 레코드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-212">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1.  <span data-ttu-id="f8317-213">레코드 **추가 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f8317-213">Select **Add record**.</span></span>

3.  <span data-ttu-id="f8317-214">사용자 **지정 DNS 레코드** 추가 창의 **유형** 드롭다운 목록에서 **CNAME(별칭)을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f8317-214">In the **Add a custom DNS record** pane, from the **Type** dropdown list, select **CNAME (Alias)**.</span></span>
4.  <span data-ttu-id="f8317-215">호스트 **이름 또는 별칭 상자에** www 를 **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="f8317-215">In the **Host name or Alias** box, type **www**.</span></span>
5.  <span data-ttu-id="f8317-216">주소 **지정 상자에** 웹 사이트의 FQDN(FQDN)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-216">In the **Points to address** box, type the fully qualified domain name (FQDN) for your website.</span></span> <span data-ttu-id="f8317-217">예를 들어 **contoso.com.**</span><span class="sxs-lookup"><span data-stu-id="f8317-217">For example, **contoso.com**.</span></span>
6.  <span data-ttu-id="f8317-218">레코드의 TTL 설정을 변경하려면 **TTL** 드롭다운 목록에서 새 기간을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-218">If you want to change the TTL setting for the record, select a new length of time from the **TTL** dropdown list.</span></span> <span data-ttu-id="f8317-219">그렇지 않은 경우 6단계를 계속 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-219">Otherwise, continue to step 6.</span></span>
7.  <span data-ttu-id="f8317-220">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-220">Select **Save**.</span></span>

<span data-ttu-id="f8317-221">Microsoft를 지점으로 이름 서비스 레코드가 업데이트된 후 도메인 설정이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-221">After the nameserver records are updated to point to Microsoft, your domain setup is complete.</span></span> <span data-ttu-id="f8317-222">전자 메일이 Microsoft로 라우팅되고, 웹 사이트 주소로의 트래픽은 계속 현재 웹 사이트 호스트로 이동됩니다.'</span><span class="sxs-lookup"><span data-stu-id="f8317-222">Email is routed to Microsoft, and traffic to your website address continues to go to your current website host.\`</span></span>
    
> [!NOTE]
> <span data-ttu-id="f8317-223">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="f8317-223">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="f8317-224">그런 다음 Microsoft 전자 메일 및 기타 서비스가 모두 도메인에서 작동하게 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8317-224">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="related-content"></a><span data-ttu-id="f8317-225">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="f8317-225">Related content</span></span>

<span data-ttu-id="f8317-226">[도메인을 연결하기](create-dns-records-at-any-dns-hosting-provider.md) 위해 DNS 레코드 추가(문서)</span><span class="sxs-lookup"><span data-stu-id="f8317-226">[Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md) (article)</span></span>\
<span data-ttu-id="f8317-227">[도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 수정](find-and-fix-issues.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="f8317-227">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>\
<span data-ttu-id="f8317-228">[도메인 관리](index.yml)(링크 페이지)</span><span class="sxs-lookup"><span data-stu-id="f8317-228">[Manage domains](index.yml) (link page)</span></span>
