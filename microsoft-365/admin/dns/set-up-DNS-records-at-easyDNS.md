---
title: EasyDNS에서 Microsoft용 DNS 레코드 만들기
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Microsoft의 easyDNS에서 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대한 DNS 레코드를 설정하는 방법을 배워야 합니다.
ms.openlocfilehash: a971a722f071ef5df9ce0fba387cfacfeb409f5b
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656822"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a><span data-ttu-id="c1bd9-103">Microsoft용 easyDNS에서 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="c1bd9-103">Create DNS records at easyDNS for Microsoft</span></span>

<span data-ttu-id="c1bd9-104">원하는 정보를 찾지 못하면 도메인 [FAQ를](../setup/domains-faq.yml) 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-104">[Check the Domains FAQ ](../setup/domains-faq.yml) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="c1bd9-105">등록 기관의 웹 사이트에서 다음 DNS 레코드를 모두 추가하여 메일을 Microsoft로 라우팅하고 Teams 및 비즈니스용 Skype에 대한 도메인을 사용하는 등 모든 DNS 레코드를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-105">You'll need to add all of the following DNS records at your registrar's website to route mail to Microsoft, use your domain for Teams and Skype for Business, and so on.</span></span>
  
<span data-ttu-id="c1bd9-106">참고: SRV 레코드는 현재 모든 easyDNS 서비스 패키지에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-106">NOTE: SRV Records are currently NOT available under all easyDNS service packages.</span></span> <span data-ttu-id="c1bd9-107">비즈니스용 Skype에 필요한 SRV 레코드를 추가하려면 easyDNS를 통해 더 높은 서비스 수준으로 업그레이드해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-107">You may need to upgrade to a higher service level with easyDNS to add SRV records which are required for Skype for Business.</span></span>
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a><span data-ttu-id="c1bd9-108">TXT 레코드가 있는 도메인을 소유하고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="c1bd9-108">Verify that you own the domain with a TXT record</span></span>

1. <span data-ttu-id="c1bd9-109">이동하여 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 자격 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-109">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="c1bd9-110">모든 **도메인 제목 아래에서** **dns를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-110">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="c1bd9-111">**TXT 레코드 제목** 아래에서 편집 단추(렌치 아이콘)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-111">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="c1bd9-112">텍스트 필드에 다음 레코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-112">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="c1bd9-113">**Host(호스트)**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-113">**Host**</span></span>|<span data-ttu-id="c1bd9-114">**Text(텍스트)**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-114">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="c1bd9-115">MS=msXXXXXXXXX(관리 센터 도메인 페이지에서 제공된 값 사용)</span><span class="sxs-lookup"><span data-stu-id="c1bd9-115">MS=msXXXXXXXX (Use the value provided to you on the admin center Domains page)</span></span>  <br/> |
   
5. <span data-ttu-id="c1bd9-116">다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-116">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="c1bd9-117">레코드가 올바른지 확인한 다음 **CONFIRM 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-117">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
7. <span data-ttu-id="c1bd9-118">방금 만든 레코드가 인터넷에 전파되고 Microsoft에서 검색될 수 있도록 계속하기 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-118">Wait a few minutes before you continue, so that the record you just created can propagate across the Internet and be detected by Microsoft.</span></span>
    
8. <span data-ttu-id="c1bd9-119">이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-119">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
    
9. <span data-ttu-id="c1bd9-120">I관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인</a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-120">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
10. <span data-ttu-id="c1bd9-121">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-121">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
11. <span data-ttu-id="c1bd9-122">설치 **페이지에서** 설치 **시작을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-122">On the **Setup** page, select **Start setup.**</span></span>
    
12. <span data-ttu-id="c1bd9-123">**도메인 확인** 페이지에서 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-123">On the **Verify domain** page, select **Verify**.</span></span> 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a><span data-ttu-id="c1bd9-124">Microsoft로 전자 메일을 라우팅하는 MX 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="c1bd9-124">Add an MX record to route email to Microsoft</span></span>

1. <span data-ttu-id="c1bd9-125">이동하여 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 자격 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-125">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="c1bd9-126">모든 **도메인 제목 아래에서** **dns를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-126">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="c1bd9-127">**MX 레코드 제목 아래에서** 편집 단추(렌치 아이콘)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-127">Under the **MX records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="c1bd9-128">텍스트 필드에 다음 레코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-128">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="c1bd9-129">**영역의 메일**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-129">**MAIL FOR ZONE**</span></span>|<span data-ttu-id="c1bd9-130">**메일 서버**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-130">**MAIL SERVER**</span></span>|<span data-ttu-id="c1bd9-131">**PREF**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-131">**PREF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="c1bd9-132">\<domain-key\>.mail.protection.outlook.com(관리 센터 \<domain-key\> 도메인 페이지에서 값 확인)</span><span class="sxs-lookup"><span data-stu-id="c1bd9-132">\<domain-key\>.mail.protection.outlook.com (Get your \<domain-key\> value from the admin center Domains page)</span></span>  <br/> |<span data-ttu-id="c1bd9-133">0</span><span class="sxs-lookup"><span data-stu-id="c1bd9-133">0</span></span>  <br/> |
   
2. <span data-ttu-id="c1bd9-134">백업을 위해 다른 MX 레코드를 저장하려는 경우 다른 MX 레코드를 다른 곳에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-134">If you want to save your other MX records for backup purposes, copy them down somewhere.</span></span> <span data-ttu-id="c1bd9-135">계속하기 전에 여기에서 다른 모든 MX 레코드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-135">Before moving on, remove all other MX records here.</span></span>
    
5. <span data-ttu-id="c1bd9-136">다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-136">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="c1bd9-137">레코드가 올바른지 확인한 다음 **CONFIRM 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-137">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-required-cname-records"></a><span data-ttu-id="c1bd9-138">필요한 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="c1bd9-138">Add the required CNAME records</span></span>

1. <span data-ttu-id="c1bd9-139">이동하여 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 자격 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-139">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="c1bd9-140">모든 **도메인 제목 아래에서** **dns를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-140">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="c1bd9-141">**CNAME/별칭** 레코드 제목 아래에서 편집 단추(렌치 아이콘)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-141">Under the **CNAME/Alias records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="c1bd9-142">텍스트 필드에 다음 레코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-142">Enter the following records in the text fields:</span></span>


    |<span data-ttu-id="c1bd9-143">**호스트**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-143">**HOST**</span></span>|<span data-ttu-id="c1bd9-144">**주소("."로 끝나야 합니다.)**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-144">**Address (Must end with a ".")**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="c1bd9-145">autodiscover</span><span class="sxs-lookup"><span data-stu-id="c1bd9-145">autodiscover</span></span>  <br/> |<span data-ttu-id="c1bd9-146">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-146">autodiscover.outlook.com.</span></span>  <br/> |
    |<span data-ttu-id="c1bd9-147">sip</span><span class="sxs-lookup"><span data-stu-id="c1bd9-147">sip</span></span>  <br/> |<span data-ttu-id="c1bd9-148">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-148">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="c1bd9-149">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="c1bd9-149">lyncdiscover</span></span>  <br/> |<span data-ttu-id="c1bd9-150">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-150">webdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="c1bd9-151">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="c1bd9-151">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="c1bd9-152">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-152">enterpriseregistration.windows.net.</span></span>  <br/> |
    |<span data-ttu-id="c1bd9-153">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="c1bd9-153">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="c1bd9-154">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-154">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |
   
5. <span data-ttu-id="c1bd9-155">다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-155">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="c1bd9-156">레코드가 올바른지 확인한 다음 **CONFIRM 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-156">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="c1bd9-157">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="c1bd9-157">Add a TXT record for SPF to help prevent email spam</span></span>

1. <span data-ttu-id="c1bd9-158">이동하여 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 자격 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-158">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="c1bd9-159">모든 **도메인 제목 아래에서** **dns를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-159">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="c1bd9-160">**TXT 레코드 제목** 아래에서 편집 단추(렌치 아이콘)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-160">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="c1bd9-161">텍스트 필드에 다음 레코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-161">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="c1bd9-162">**Host(호스트)**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-162">**Host**</span></span>|<span data-ttu-id="c1bd9-163">**Text(텍스트)**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-163">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="c1bd9-164">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="c1bd9-164">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> |
   
5. <span data-ttu-id="c1bd9-165">다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-165">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="c1bd9-166">레코드가 올바른지 확인한 다음 **CONFIRM 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-166">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="c1bd9-167">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="c1bd9-167">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="c1bd9-168">참고: SRV 레코드는 현재 easyDNS의 Domain Plus 서비스 수준에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-168">NOTE: SRV Records are currently NOT available under easyDNS' Domain Plus service level.</span></span> <span data-ttu-id="c1bd9-169">SRV 레코드를 추가하려면 easyDNS를 통해 더 높은 서비스 수준으로 업그레이드해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-169">You may need to upgrade to a higher service level with easyDNS to add SRV records</span></span> 
  
1. <span data-ttu-id="c1bd9-170">이동하여 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 자격 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-170">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="c1bd9-171">모든 **도메인 제목 아래에서** **dns를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-171">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="c1bd9-172">**SRV 레코드** 제목 아래에서 편집 단추(렌치 아이콘)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-172">Under the **SRV records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="c1bd9-173">텍스트 필드에 다음 레코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-173">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="c1bd9-174">**서비스**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-174">**SERVICE**</span></span>|<span data-ttu-id="c1bd9-175">**PROTO**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-175">**PROTO**</span></span>|<span data-ttu-id="c1bd9-176">**호스트**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-176">**HOST**</span></span>|<span data-ttu-id="c1bd9-177">**PRI**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-177">**PRI**</span></span>|<span data-ttu-id="c1bd9-178">**WGT**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-178">**WGT**</span></span>|<span data-ttu-id="c1bd9-179">**포트**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-179">**PORT**</span></span>|<span data-ttu-id="c1bd9-180">**TARGET("."로 끝나야 합니다.)**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-180">**TARGET(Must end with a ".")**</span></span>|<span data-ttu-id="c1bd9-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-181">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c1bd9-182">_sip</span><span class="sxs-lookup"><span data-stu-id="c1bd9-182">_sip</span></span>  <br/> |<span data-ttu-id="c1bd9-183">TLS</span><span class="sxs-lookup"><span data-stu-id="c1bd9-183">TLS</span></span>  <br/> |@  <br/> |<span data-ttu-id="c1bd9-184">100</span><span class="sxs-lookup"><span data-stu-id="c1bd9-184">100</span></span>  <br/> |<span data-ttu-id="c1bd9-185">1 </span><span class="sxs-lookup"><span data-stu-id="c1bd9-185">1</span></span>  <br/> |<span data-ttu-id="c1bd9-186">443</span><span class="sxs-lookup"><span data-stu-id="c1bd9-186">443</span></span>  <br/> |<span data-ttu-id="c1bd9-187">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-187">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="c1bd9-188">1800</span><span class="sxs-lookup"><span data-stu-id="c1bd9-188">1800</span></span>  <br/> |
    |<span data-ttu-id="c1bd9-189">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="c1bd9-189">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="c1bd9-190">TCP</span><span class="sxs-lookup"><span data-stu-id="c1bd9-190">TCP</span></span>  <br/> |@  <br/> |<span data-ttu-id="c1bd9-191">100</span><span class="sxs-lookup"><span data-stu-id="c1bd9-191">100</span></span>  <br/> |<span data-ttu-id="c1bd9-192">1 </span><span class="sxs-lookup"><span data-stu-id="c1bd9-192">1</span></span>  <br/> |<span data-ttu-id="c1bd9-193">5061</span><span class="sxs-lookup"><span data-stu-id="c1bd9-193">5061</span></span>  <br/> |<span data-ttu-id="c1bd9-194">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="c1bd9-194">sipfed.online.lync.com.</span></span>  <br/> |<span data-ttu-id="c1bd9-195">1800</span><span class="sxs-lookup"><span data-stu-id="c1bd9-195">1800</span></span>  <br/> |
   
5. <span data-ttu-id="c1bd9-196">다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-196">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="c1bd9-197">레코드가 올바른지 확인한 다음 **CONFIRM 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c1bd9-197">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    

