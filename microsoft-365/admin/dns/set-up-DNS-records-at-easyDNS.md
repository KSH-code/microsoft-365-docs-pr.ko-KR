---
title: EasyDNS에서 Microsoft에 대 한 DNS 레코드 만들기
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대 한 DNS 레코드를 Microsoft 용 easyDNS에 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: b7b29900108ab94f0fd99dcf3404cfa137ce92ff
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631360"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a><span data-ttu-id="7490f-103">EasyDNS에서 Microsoft에 대 한 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="7490f-103">Create DNS records at easyDNS for Microsoft</span></span>

<span data-ttu-id="7490f-104">원하는 정보를 찾지 못한 경우 [도메인 FAQ를 확인](../setup/domains-faq.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="7490f-105">Microsoft로 메일을 라우팅하기 위해 등록자의 웹 사이트에서 다음 DNS 레코드를 모두 추가 하 고, 팀과 비즈니스용 Skype 등에 대해 도메인을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-105">You'll need to add all of the following DNS records at your registrar's website to route mail to Microsoft, use your domain for Teams and Skype for Business, and so on.</span></span>
  
<span data-ttu-id="7490f-106">참고: SRV 레코드는 현재 모든 easyDNS 서비스 패키지에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-106">NOTE: SRV Records are currently NOT available under all easyDNS service packages.</span></span> <span data-ttu-id="7490f-107">비즈니스용 Skype에 필요한 SRV 레코드를 추가 하려면 easyDNS를 사용 하 여 더 높은 수준의 서비스 수준으로 업그레이드 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-107">You may need to upgrade to a higher service level with easyDNS to add SRV records which are required for Skype for Business.</span></span>
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a><span data-ttu-id="7490f-108">TXT 레코드를 사용 하 여 도메인을 소유 하 고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="7490f-108">Verify that you own the domain with a TXT record</span></span>

1. <span data-ttu-id="7490f-109">[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 으로 이동 하 여 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-109">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="7490f-110">**모든 도메인** 머리글에서 dns를 선택 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="7490f-110">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="7490f-111">**TXT 레코드** 제목 아래에서 편집 단추 (렌치 아이콘)를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-111">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="7490f-112">텍스트 필드에 다음 레코드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-112">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="7490f-113">**Host(호스트)**</span><span class="sxs-lookup"><span data-stu-id="7490f-113">**Host**</span></span>|<span data-ttu-id="7490f-114">**텍스트**</span><span class="sxs-lookup"><span data-stu-id="7490f-114">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="7490f-115">MS = msXXXXXXXX (관리 센터 도메인에 제공 된 값 사용 페이지)</span><span class="sxs-lookup"><span data-stu-id="7490f-115">MS=msXXXXXXXX (Use the value provided to you on the admin center Domains page)</span></span>  <br/> |
   
5. <span data-ttu-id="7490f-116">**다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-116">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="7490f-117">레코드가 올바른지 확인 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-117">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
7. <span data-ttu-id="7490f-118">방금 만든 레코드가 인터넷을 통해 전파 되 고 Microsoft에서 검색할 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-118">Wait a few minutes before you continue, so that the record you just created can propagate across the Internet and be detected by Microsoft.</span></span>
    
8. <span data-ttu-id="7490f-119">도메인 등록 기관 사이트에서 레코드를 추가 했으므로 이제 Microsoft로 이동 하 여 레코드를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-119">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
    
9. <span data-ttu-id="7490f-120">I관리 센터에서 \*\* 설정 \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="7490f-120">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
10. <span data-ttu-id="7490f-121">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-121">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
11. <span data-ttu-id="7490f-122">**설정** 페이지에서 **설정 시작을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="7490f-122">On the **Setup** page, select **Start setup.**</span></span>
    
12. <span data-ttu-id="7490f-123">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-123">On the **Verify domain** page, select **Verify**.</span></span> 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a><span data-ttu-id="7490f-124">Microsoft에 전자 메일을 라우팅하기 위한 MX 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="7490f-124">Add an MX record to route email to Microsoft</span></span>

1. <span data-ttu-id="7490f-125">[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 으로 이동 하 여 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-125">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="7490f-126">**모든 도메인** 머리글에서 dns를 선택 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="7490f-126">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="7490f-127">**MX 레코드** 제목 아래에서 편집 단추 (렌치 아이콘)를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-127">Under the **MX records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="7490f-128">텍스트 필드에 다음 레코드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-128">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="7490f-129">**영역에 대 한 메일**</span><span class="sxs-lookup"><span data-stu-id="7490f-129">**MAIL FOR ZONE**</span></span>|<span data-ttu-id="7490f-130">**메일 서버**</span><span class="sxs-lookup"><span data-stu-id="7490f-130">**MAIL SERVER**</span></span>|<span data-ttu-id="7490f-131">**우선**</span><span class="sxs-lookup"><span data-stu-id="7490f-131">**PREF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="7490f-132">\<\>mail.protection.outlook.com (관리 센터 도메인 페이지에서 \<도메인 키\> 값 가져오기)</span><span class="sxs-lookup"><span data-stu-id="7490f-132">\<domain-key\>.mail.protection.outlook.com (Get your \<domain-key\> value from the admin center Domains page)</span></span>  <br/> |<span data-ttu-id="7490f-133">개</span><span class="sxs-lookup"><span data-stu-id="7490f-133">0</span></span>  <br/> |
   
2. <span data-ttu-id="7490f-134">백업 목적으로 다른 MX 레코드를 저장 하려면 그 위치에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-134">If you want to save your other MX records for backup purposes, copy them down somewhere.</span></span> <span data-ttu-id="7490f-135">이동 하기 전에 여기에서 다른 모든 MX 레코드를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-135">Before moving on, remove all other MX records here.</span></span>
    
5. <span data-ttu-id="7490f-136">**다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-136">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="7490f-137">레코드가 올바른지 확인 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-137">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-required-cname-records"></a><span data-ttu-id="7490f-138">필요한 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="7490f-138">Add the required CNAME records</span></span>

1. <span data-ttu-id="7490f-139">[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 으로 이동 하 여 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-139">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="7490f-140">**모든 도메인** 머리글에서 dns를 선택 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="7490f-140">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="7490f-141">**CNAME/별칭 레코드** 제목에서 편집 단추 (렌치 아이콘)를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-141">Under the **CNAME/Alias records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="7490f-142">텍스트 필드에 다음 레코드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-142">Enter the following records in the text fields:</span></span>


    |<span data-ttu-id="7490f-143">**호스트**</span><span class="sxs-lookup"><span data-stu-id="7490f-143">**HOST**</span></span>|<span data-ttu-id="7490f-144">**주소 ("."로 끝나야 함)**</span><span class="sxs-lookup"><span data-stu-id="7490f-144">**Address (Must end with a ".")**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="7490f-145">autodiscover</span><span class="sxs-lookup"><span data-stu-id="7490f-145">autodiscover</span></span>  <br/> |<span data-ttu-id="7490f-146">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="7490f-146">autodiscover.outlook.com.</span></span>  <br/> |
    |<span data-ttu-id="7490f-147">sip</span><span class="sxs-lookup"><span data-stu-id="7490f-147">sip</span></span>  <br/> |<span data-ttu-id="7490f-148">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7490f-148">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="7490f-149">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="7490f-149">lyncdiscover</span></span>  <br/> |<span data-ttu-id="7490f-150">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7490f-150">webdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="7490f-151">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="7490f-151">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="7490f-152">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="7490f-152">enterpriseregistration.windows.net.</span></span>  <br/> |
    |<span data-ttu-id="7490f-153">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="7490f-153">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="7490f-154">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7490f-154">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |
   
5. <span data-ttu-id="7490f-155">**다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-155">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="7490f-156">레코드가 올바른지 확인 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-156">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="7490f-157">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="7490f-157">Add a TXT record for SPF to help prevent email spam</span></span>

1. <span data-ttu-id="7490f-158">[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 으로 이동 하 여 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-158">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="7490f-159">**모든 도메인** 머리글에서 dns를 선택 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="7490f-159">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="7490f-160">**TXT 레코드** 제목 아래에서 편집 단추 (렌치 아이콘)를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-160">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="7490f-161">텍스트 필드에 다음 레코드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-161">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="7490f-162">**Host(호스트)**</span><span class="sxs-lookup"><span data-stu-id="7490f-162">**Host**</span></span>|<span data-ttu-id="7490f-163">**텍스트**</span><span class="sxs-lookup"><span data-stu-id="7490f-163">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="7490f-164">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="7490f-164">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> |
   
5. <span data-ttu-id="7490f-165">**다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-165">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="7490f-166">레코드가 올바른지 확인 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-166">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="7490f-167">Microsoft에 필요한 두 개의 SRV 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-167">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="7490f-168">참고: easyDNS ' 도메인 Plus 서비스 수준 '에서는 현재 SRV 레코드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-168">NOTE: SRV Records are currently NOT available under easyDNS' Domain Plus service level.</span></span> <span data-ttu-id="7490f-169">SRV 레코드를 추가 하려면 easyDNS를 사용 하 여 더 높은 서비스 수준으로 업그레이드 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-169">You may need to upgrade to a higher service level with easyDNS to add SRV records</span></span> 
  
1. <span data-ttu-id="7490f-170">[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 으로 이동 하 여 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-170">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="7490f-171">**모든 도메인** 머리글에서 dns를 선택 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="7490f-171">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="7490f-172">**SRV 레코드** 제목 아래에서 편집 단추 (렌치 아이콘)를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-172">Under the **SRV records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="7490f-173">텍스트 필드에 다음 레코드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-173">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="7490f-174">**서비스**</span><span class="sxs-lookup"><span data-stu-id="7490f-174">**SERVICE**</span></span>|<span data-ttu-id="7490f-175">**프로토콜**</span><span class="sxs-lookup"><span data-stu-id="7490f-175">**PROTO**</span></span>|<span data-ttu-id="7490f-176">**호스트**</span><span class="sxs-lookup"><span data-stu-id="7490f-176">**HOST**</span></span>|<span data-ttu-id="7490f-177">**PRI**</span><span class="sxs-lookup"><span data-stu-id="7490f-177">**PRI**</span></span>|<span data-ttu-id="7490f-178">**WGT**</span><span class="sxs-lookup"><span data-stu-id="7490f-178">**WGT**</span></span>|<span data-ttu-id="7490f-179">**포트**</span><span class="sxs-lookup"><span data-stu-id="7490f-179">**PORT**</span></span>|<span data-ttu-id="7490f-180">**대상 ("."로 끝나야 함)**</span><span class="sxs-lookup"><span data-stu-id="7490f-180">**TARGET(Must end with a ".")**</span></span>|<span data-ttu-id="7490f-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7490f-181">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7490f-182">_sip</span><span class="sxs-lookup"><span data-stu-id="7490f-182">_sip</span></span>  <br/> |<span data-ttu-id="7490f-183">TLS</span><span class="sxs-lookup"><span data-stu-id="7490f-183">TLS</span></span>  <br/> |@  <br/> |<span data-ttu-id="7490f-184">100</span><span class="sxs-lookup"><span data-stu-id="7490f-184">100</span></span>  <br/> |<span data-ttu-id="7490f-185">1 </span><span class="sxs-lookup"><span data-stu-id="7490f-185">1</span></span>  <br/> |<span data-ttu-id="7490f-186">443</span><span class="sxs-lookup"><span data-stu-id="7490f-186">443</span></span>  <br/> |<span data-ttu-id="7490f-187">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7490f-187">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="7490f-188">1800</span><span class="sxs-lookup"><span data-stu-id="7490f-188">1800</span></span>  <br/> |
    |<span data-ttu-id="7490f-189">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="7490f-189">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="7490f-190">TCP</span><span class="sxs-lookup"><span data-stu-id="7490f-190">TCP</span></span>  <br/> |@  <br/> |<span data-ttu-id="7490f-191">100</span><span class="sxs-lookup"><span data-stu-id="7490f-191">100</span></span>  <br/> |<span data-ttu-id="7490f-192">1 </span><span class="sxs-lookup"><span data-stu-id="7490f-192">1</span></span>  <br/> |<span data-ttu-id="7490f-193">5061</span><span class="sxs-lookup"><span data-stu-id="7490f-193">5061</span></span>  <br/> |<span data-ttu-id="7490f-194">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7490f-194">sipfed.online.lync.com.</span></span>  <br/> |<span data-ttu-id="7490f-195">1800</span><span class="sxs-lookup"><span data-stu-id="7490f-195">1800</span></span>  <br/> |
   
5. <span data-ttu-id="7490f-196">**다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-196">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="7490f-197">레코드가 올바른지 확인 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7490f-197">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    

