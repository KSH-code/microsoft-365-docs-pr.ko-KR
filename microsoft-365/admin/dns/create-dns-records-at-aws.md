---
title: AWS(Amazon Web Services)에서 Microsoft용 DNS 레코드 만들기
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
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: AWS(Amazon Web Services)에서 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대한 DNS 레코드를 설정하는 방법을 자세히 알아보십시오.
ms.openlocfilehash: bb687b8685aed79f5f768c12d652205bbbed0f59
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657975"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-microsoft"></a><span data-ttu-id="8af76-103">AWS(Amazon Web Services)에서 Microsoft용 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="8af76-103">Create DNS records at Amazon Web Services (AWS) for Microsoft</span></span>

 <span data-ttu-id="8af76-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="8af76-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="8af76-105">DNS 호스팅 공급자로 AWS를 사용하고 있는 경우 이 문서의 단계에 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online에 대한 DNS 레코드를 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="8af76-105">If AWS is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype Online for Business, and so on.</span></span>
  
<span data-ttu-id="8af76-106">AWS에서 이러한 레코드를 추가하고 나면 도메인이 Microsoft 서비스와 함께 작동할 수 있도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-106">After you add these records at AWS, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="8af76-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="8af76-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="8af76-108">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="8af76-109">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8af76-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="8af76-110">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="8af76-110">Add a TXT record for verification</span></span>
<span data-ttu-id="8af76-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="8af76-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="8af76-p102">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8af76-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="8af76-p104">시작하려면 [이 링크](https://console.aws.amazon.com/route53/home)를 사용하여 AWS의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="8af76-118">리소스 **페이지에서** 호스팅된 **영역 선택**</span><span class="sxs-lookup"><span data-stu-id="8af76-118">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="8af76-119">호스팅된 **영역** 페이지의 도메인 **이름** 열에서 편집할 도메인의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-119">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="8af76-120">레코드 **집합 만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8af76-120">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="8af76-121">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="8af76-121">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="8af76-122">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="8af76-122">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="8af76-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="8af76-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8af76-125">**이름**</span><span class="sxs-lookup"><span data-stu-id="8af76-125">**Name**</span></span> <br/> |<span data-ttu-id="8af76-126">**Type(종류)**</span><span class="sxs-lookup"><span data-stu-id="8af76-126">**Type**</span></span> <br/> |<span data-ttu-id="8af76-127">**별칭**</span><span class="sxs-lookup"><span data-stu-id="8af76-127">**Alias**</span></span> <br/> |<span data-ttu-id="8af76-128">**TTL(초)**</span><span class="sxs-lookup"><span data-stu-id="8af76-128">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="8af76-129">**값**</span><span class="sxs-lookup"><span data-stu-id="8af76-129">**Value**</span></span> <br/> |<span data-ttu-id="8af76-130">**라우팅 정책**</span><span class="sxs-lookup"><span data-stu-id="8af76-130">**Routing Policy**</span></span> <br/> |
    |<span data-ttu-id="8af76-131">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="8af76-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="8af76-132">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="8af76-132">TXT - Text</span></span>  <br/> |<span data-ttu-id="8af76-133">아니요</span><span class="sxs-lookup"><span data-stu-id="8af76-133">No</span></span>  <br/> |<span data-ttu-id="8af76-134">300</span><span class="sxs-lookup"><span data-stu-id="8af76-134">300</span></span>  <br/> |<span data-ttu-id="8af76-135">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="8af76-135">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="8af76-136">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-136">**Note:** This is an example.</span></span> <span data-ttu-id="8af76-137">여기에는 Microsoft 365의 표에 있는 특정 **주소를 지정할 대상 또는 지점** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-137">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span> [<span data-ttu-id="8af76-138">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="8af76-138">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="8af76-139">Simple(단순형)</span><span class="sxs-lookup"><span data-stu-id="8af76-139">Simple</span></span>  <br/> |
   
6. <span data-ttu-id="8af76-140">**만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-140">Select **Create**.</span></span>
    
7. <span data-ttu-id="8af76-141">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="8af76-142">이제 도메인 등록 기관의 사이트에 레코드를 추가한 후 Microsoft로 돌아가서 레코드에 대한 검색을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-142">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="8af76-143">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-143">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="8af76-144">Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-144">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="8af76-145">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="8af76-146">**설정** 페이지에서 **설정 시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-146">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="8af76-147">**도메인 확인** 페이지에서 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-147">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8af76-148">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="8af76-148">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="8af76-149">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-149">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="8af76-150">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8af76-150">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a><span data-ttu-id="8af76-151">도메인의 전자 메일이 Microsoft 365로 전송될 수 있도록 MX 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="8af76-151">Add an MX record so email for your domain will come to Microsoft 365</span></span>
<span data-ttu-id="8af76-152"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="8af76-152"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="8af76-p108">시작하려면 [이 링크](https://console.aws.amazon.com/route53/home)를 사용하여 AWS의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-p108">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="8af76-155">리소스 **페이지에서** 호스팅된 **영역 선택**</span><span class="sxs-lookup"><span data-stu-id="8af76-155">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="8af76-156">호스팅된 **영역** 페이지의 도메인 **이름** 열에서 편집할 도메인의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-156">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="8af76-157">레코드 **집합 만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8af76-157">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="8af76-158">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="8af76-158">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="8af76-159">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="8af76-159">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="8af76-160">**이름**</span><span class="sxs-lookup"><span data-stu-id="8af76-160">**Name**</span></span>|<span data-ttu-id="8af76-161">**Type(종류)**</span><span class="sxs-lookup"><span data-stu-id="8af76-161">**Type**</span></span>|<span data-ttu-id="8af76-162">**별칭**</span><span class="sxs-lookup"><span data-stu-id="8af76-162">**Alias**</span></span>|<span data-ttu-id="8af76-163">**TTL(초)**</span><span class="sxs-lookup"><span data-stu-id="8af76-163">**TTL (Seconds)**</span></span>|<span data-ttu-id="8af76-164">**값**</span><span class="sxs-lookup"><span data-stu-id="8af76-164">**Value**</span></span>|<span data-ttu-id="8af76-165">**라우팅 정책**</span><span class="sxs-lookup"><span data-stu-id="8af76-165">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8af76-166">(이 필드는 비워 둡니다.)</span><span class="sxs-lookup"><span data-stu-id="8af76-166">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="8af76-167">MX - Mail Exchanger(MX - 메일 교환기)</span><span class="sxs-lookup"><span data-stu-id="8af76-167">MX - Mail exchange</span></span>  <br/> |<span data-ttu-id="8af76-168">No(아니요)</span><span class="sxs-lookup"><span data-stu-id="8af76-168">No</span></span>  <br/> |<span data-ttu-id="8af76-169">300</span><span class="sxs-lookup"><span data-stu-id="8af76-169">300</span></span>  <br/> |<span data-ttu-id="8af76-170">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="8af76-170">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="8af76-p109">0은 MX 우선 순위 값입니다. 이 값을 MX 값 시작 부분에 추가하고 나머지 값과 공백으로 구분합니다.  </span><span class="sxs-lookup"><span data-stu-id="8af76-p109">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="8af76-173">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8af76-173">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="8af76-174">**참고:** Microsoft \<*domain-key*\> 365 계정에서 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="8af76-174">**Note:** Get your \<*domain-key*\> from your Microsoft 365 account.</span></span> [<span data-ttu-id="8af76-175">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="8af76-175">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="8af76-176">Simple(단순형)</span><span class="sxs-lookup"><span data-stu-id="8af76-176">Simple</span></span>  <br/> |
       
    ![AWS-BP-Configure-2-1](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. <span data-ttu-id="8af76-178">**만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-178">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. <span data-ttu-id="8af76-180">다른 MX 레코드가 있으면 해당 레코드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-180">If there are any other MX records, remove them.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8af76-181">AWS에서는 MX 레코드를 여러 레코드가 포함될 수 있는 한 집합으로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-181">AWS stores MX records as a set that may contain multiple records.</span></span> <span data-ttu-id="8af76-182">**방금 추가한** 레코드를 포함하여 모든 MX 레코드가 삭제됩니다. 레코드 집합 삭제를 선택하지 않습니다. </span><span class="sxs-lookup"><span data-stu-id="8af76-182">**DO NOT** select **Delete Record Set**, as this will delete all of your MX records, including the one you just added.</span></span> <span data-ttu-id="8af76-183">대신 다음 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-183">Use the following instructions instead.</span></span> 
  
    <span data-ttu-id="8af76-184">먼저 MX 레코드 집합을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-184">First, select the MX record set.</span></span>
    
    ![AWS-BP-Configure-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    <span data-ttu-id="8af76-186">다음으로, **Edit Record Set(레코드 집합 편집)** 영역의 **Value(값)** 상자에서 항목을 선택한 다음 키보드의 **Delete** 키를 눌러 오래된 각 MX 레코드를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-186">Next, in the **Edit Record Set** area, delete each obsolete MX record by selecting the entry in the **Value** box and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![AWS-BP-Configure-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. <span data-ttu-id="8af76-188">레코드 **저장 집합을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8af76-188">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="8af76-190">Microsoft 365에 필요한 5개의 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="8af76-190">Add the five CNAME records that are required for Microsoft 365</span></span>
<span data-ttu-id="8af76-191"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="8af76-191"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="8af76-p112">시작하려면 [이 링크](https://console.aws.amazon.com/route53/home)를 사용하여 AWS의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-p112">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="8af76-194">리소스 **페이지에서** 호스팅된 **영역 선택**</span><span class="sxs-lookup"><span data-stu-id="8af76-194">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="8af76-195">호스팅된 **영역** 페이지의 도메인 **이름** 열에서 편집할 도메인의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-195">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="8af76-196">레코드 **집합 만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8af76-196">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="8af76-197">첫 번째 CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-197">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="8af76-198">**Create Record Set(레코드 집합 만들기)** 영역의 새 레코드용 상자에 다음 표의 첫 번째 행에 있는 값을 입력하거나 복사하여 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-198">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="8af76-199">(드롭다운 목록에서 **Type**(종류) 및 **Routing Policy**(라우팅 정책) 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="8af76-199">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="8af76-200">**이름**</span><span class="sxs-lookup"><span data-stu-id="8af76-200">**Name**</span></span>|<span data-ttu-id="8af76-201">**Type(종류)**</span><span class="sxs-lookup"><span data-stu-id="8af76-201">**Type**</span></span>|<span data-ttu-id="8af76-202">**별칭**</span><span class="sxs-lookup"><span data-stu-id="8af76-202">**Alias**</span></span>|<span data-ttu-id="8af76-203">**TTL(초)**</span><span class="sxs-lookup"><span data-stu-id="8af76-203">**TTL (Seconds)**</span></span>|<span data-ttu-id="8af76-204">**값**</span><span class="sxs-lookup"><span data-stu-id="8af76-204">**Value**</span></span>|<span data-ttu-id="8af76-205">**라우팅 정책**</span><span class="sxs-lookup"><span data-stu-id="8af76-205">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8af76-206">autodiscover</span><span class="sxs-lookup"><span data-stu-id="8af76-206">autodiscover</span></span>  <br/> |<span data-ttu-id="8af76-207">CNAME - Canonical name(CNAME - 정식 이름)</span><span class="sxs-lookup"><span data-stu-id="8af76-207">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="8af76-208">No(아니요)</span><span class="sxs-lookup"><span data-stu-id="8af76-208">No</span></span>  <br/> |<span data-ttu-id="8af76-209">300</span><span class="sxs-lookup"><span data-stu-id="8af76-209">300</span></span>  <br/> |<span data-ttu-id="8af76-210">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="8af76-210">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="8af76-211">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8af76-211">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="8af76-212">Simple(기본)</span><span class="sxs-lookup"><span data-stu-id="8af76-212">Simple</span></span>  <br/> |
    |<span data-ttu-id="8af76-213">sip</span><span class="sxs-lookup"><span data-stu-id="8af76-213">sip</span></span>  <br/> |<span data-ttu-id="8af76-214">CNAME - Canonical name(CNAME - 정식 이름)</span><span class="sxs-lookup"><span data-stu-id="8af76-214">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="8af76-215">No(아니요)</span><span class="sxs-lookup"><span data-stu-id="8af76-215">No</span></span>  <br/> |<span data-ttu-id="8af76-216">300</span><span class="sxs-lookup"><span data-stu-id="8af76-216">300</span></span>  <br/> |<span data-ttu-id="8af76-217">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8af76-217">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="8af76-218">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8af76-218">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="8af76-219">Simple(기본)</span><span class="sxs-lookup"><span data-stu-id="8af76-219">Simple</span></span>  <br/> |
    |<span data-ttu-id="8af76-220">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="8af76-220">lyncdiscover</span></span>  <br/> |<span data-ttu-id="8af76-221">CNAME - Canonical name(CNAME - 정식 이름)</span><span class="sxs-lookup"><span data-stu-id="8af76-221">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="8af76-222">No(아니요)</span><span class="sxs-lookup"><span data-stu-id="8af76-222">No</span></span>  <br/> |<span data-ttu-id="8af76-223">300</span><span class="sxs-lookup"><span data-stu-id="8af76-223">300</span></span>  <br/> |<span data-ttu-id="8af76-224">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8af76-224">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="8af76-225">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8af76-225">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="8af76-226">Simple(단순형)</span><span class="sxs-lookup"><span data-stu-id="8af76-226">Simple</span></span>  <br/> |
    |<span data-ttu-id="8af76-227">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="8af76-227">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="8af76-228">CNAME - Canonical name(CNAME - 정식 이름)</span><span class="sxs-lookup"><span data-stu-id="8af76-228">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="8af76-229">No(아니요)</span><span class="sxs-lookup"><span data-stu-id="8af76-229">No</span></span>  <br/> |<span data-ttu-id="8af76-230">300</span><span class="sxs-lookup"><span data-stu-id="8af76-230">300</span></span>  <br/> |<span data-ttu-id="8af76-231">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="8af76-231">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="8af76-232">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8af76-232">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="8af76-233">Simple(기본)</span><span class="sxs-lookup"><span data-stu-id="8af76-233">Simple</span></span>  <br/> |
    |<span data-ttu-id="8af76-234">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="8af76-234">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="8af76-235">CNAME - Canonical name(CNAME - 정식 이름)</span><span class="sxs-lookup"><span data-stu-id="8af76-235">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="8af76-236">No(아니요)</span><span class="sxs-lookup"><span data-stu-id="8af76-236">No</span></span>  <br/> |<span data-ttu-id="8af76-237">300</span><span class="sxs-lookup"><span data-stu-id="8af76-237">300</span></span>  <br/> |<span data-ttu-id="8af76-238">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="8af76-238">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="8af76-239">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8af76-239">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="8af76-240">Simple(단순형)</span><span class="sxs-lookup"><span data-stu-id="8af76-240">Simple</span></span>  <br/> |
   
    ![AWS-BP-Configure-3-1](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. <span data-ttu-id="8af76-242">**만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-242">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. <span data-ttu-id="8af76-244">나머지 4개의 CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-244">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="8af76-245">호스팅된  영역 페이지에서 레코드 집합 만들기를 선택하고 **표의** 다음 행 값을 사용하여 레코드를 만든  다음 만들기를 다시 선택하여 해당 레코드를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-245">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
    <span data-ttu-id="8af76-246">5개의 CNAME 레코드를 모두 만들 때까지 이 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-246">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="8af76-247">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="8af76-247">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="8af76-248"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="8af76-248"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="8af76-249">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-249">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="8af76-250">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-250">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="8af76-251">도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="8af76-251">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="8af76-252">대신 두 값 집합을 모두 포함하는  *단일*  SPF 레코드가 있도록 현재 레코드에 필요한 Microsoft 값을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-252">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="8af76-253">예제가 필요하세요?</span><span class="sxs-lookup"><span data-stu-id="8af76-253">Need examples?</span></span> <span data-ttu-id="8af76-254">[Microsoft에 대한 외부 Domain Name System 레코드](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8af76-254">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="8af76-255">SPF 레코드의 유효성을 검사하기 위해 다음 SPF 유효성 검사 도구 중[하나를 사용할 수 있습니다.](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="8af76-255">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="8af76-256">시작하려면 [이 링크](https://console.aws.amazon.com/route53/home)를 사용하여 AWS의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-256">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="8af76-257">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-257">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="8af76-258">리소스 **페이지에서** 호스팅된 **영역 선택**</span><span class="sxs-lookup"><span data-stu-id="8af76-258">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="8af76-259">호스팅된 **영역** 페이지의 도메인 **이름** 열에서 편집할 도메인의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-259">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="8af76-260">**TXT 레코드 집합을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-260">Select the **TXT** record set.</span></span> 
    
    ![AWS-BP-Configure-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. <span data-ttu-id="8af76-p115">**레코드 집합 편집** 영역에서 기존 레코드의 **값:** 상자에 있는 현재 항목의 맨 끝에서 키보드의 Enter를 눌러 새 줄을 만든 다음, 이 새 줄에서(기존 값 아래) 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. (표 아래 그림의 예를 참조할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="8af76-p115">In the **Edit Record Set** area, at the end of the current entry in the **Value:** box for the existing record, press Enter on your keyboard to create a new line; and then, on that new line (under the existing value), type or copy and paste the value from the following table. (You can see an example in the illustration below the table.)</span></span> 
    
    |<span data-ttu-id="8af76-264">**값:**</span><span class="sxs-lookup"><span data-stu-id="8af76-264">**Value:**</span></span>|
    |:-----|
    |<span data-ttu-id="8af76-265">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="8af76-265">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="8af76-p116">(화면 지침에 필요한 물음표가 자동으로 제공됩니다. 직접 입력할 필요가 없습니다.)  </span><span class="sxs-lookup"><span data-stu-id="8af76-p116">(The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.)  </span></span><br/> <span data-ttu-id="8af76-268">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-268">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![AWS-BP-Configure-4-2](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. <span data-ttu-id="8af76-270">레코드 **저장 집합을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8af76-270">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="8af76-272">Microsoft 365에 필요한 2개의 SRV 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="8af76-272">Add the two SRV records that are required for Microsoft 365</span></span>
<span data-ttu-id="8af76-273"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="8af76-273"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="8af76-p117">시작하려면 [이 링크](https://console.aws.amazon.com/route53/home)를 사용하여 AWS의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-p117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="8af76-276">리소스 **페이지에서** 호스팅된 **영역 선택**</span><span class="sxs-lookup"><span data-stu-id="8af76-276">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="8af76-277">호스팅된 **영역** 페이지의 도메인 **이름** 열에서 편집할 도메인의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-277">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="8af76-278">레코드 **집합 만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8af76-278">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="8af76-279">첫 번째 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-279">Add the first SRV record:</span></span>
    
    <span data-ttu-id="8af76-280">**Create Record Set(레코드 집합 만들기)** 영역의 새 레코드용 상자에 다음 표의 첫 번째 행에 있는 값을 입력하거나 복사하여 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-280">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="8af76-281">(드롭다운 목록에서 **Type**(종류) 및 **Routing Policy**(라우팅 정책) 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="8af76-281">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="8af76-282">**이름**</span><span class="sxs-lookup"><span data-stu-id="8af76-282">**Name**</span></span>|<span data-ttu-id="8af76-283">**Type(종류)**</span><span class="sxs-lookup"><span data-stu-id="8af76-283">**Type**</span></span>|<span data-ttu-id="8af76-284">**별칭**</span><span class="sxs-lookup"><span data-stu-id="8af76-284">**Alias**</span></span>|<span data-ttu-id="8af76-285">**TTL(초)**</span><span class="sxs-lookup"><span data-stu-id="8af76-285">**TTL (Seconds)**</span></span>|<span data-ttu-id="8af76-286">**값**</span><span class="sxs-lookup"><span data-stu-id="8af76-286">**Value**</span></span>|<span data-ttu-id="8af76-287">**라우팅 정책**</span><span class="sxs-lookup"><span data-stu-id="8af76-287">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8af76-288">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="8af76-288">_sip._tls</span></span>|<span data-ttu-id="8af76-289">SRV - Service locator(SRV - 서비스 로케이터)</span><span class="sxs-lookup"><span data-stu-id="8af76-289">SRV - Service locator</span></span>|<span data-ttu-id="8af76-290">아니요</span><span class="sxs-lookup"><span data-stu-id="8af76-290">No</span></span>|<span data-ttu-id="8af76-291">300</span><span class="sxs-lookup"><span data-stu-id="8af76-291">300</span></span>|<span data-ttu-id="8af76-292">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8af76-292">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="8af76-293">**이 값은 기간(.)으로 끝나야 합니다.**></span><span class="sxs-lookup"><span data-stu-id="8af76-293">**This value MUST end with a period (.)**></span></span><br> <span data-ttu-id="8af76-294">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-294">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="8af76-295">Simple(단순형)</span><span class="sxs-lookup"><span data-stu-id="8af76-295">Simple</span></span>|
    |<span data-ttu-id="8af76-296">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="8af76-296">_sipfederationtls._tcp</span></span>|<span data-ttu-id="8af76-297">SRV - Service locator(SRV - 서비스 로케이터)</span><span class="sxs-lookup"><span data-stu-id="8af76-297">SRV - Service locator</span></span>|<span data-ttu-id="8af76-298">아니요</span><span class="sxs-lookup"><span data-stu-id="8af76-298">No</span></span>|<span data-ttu-id="8af76-299">300</span><span class="sxs-lookup"><span data-stu-id="8af76-299">300</span></span>|<span data-ttu-id="8af76-300">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8af76-300">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="8af76-301">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8af76-301">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="8af76-302">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-302">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="8af76-303">기본형</span><span class="sxs-lookup"><span data-stu-id="8af76-303">Simple</span></span>|
   
    ![AWS-BP-Configure-5-1](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. <span data-ttu-id="8af76-305">**만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-305">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. <span data-ttu-id="8af76-307">다른 SRV 레코드를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="8af76-307">To add the other SRV record:</span></span>
    
    <span data-ttu-id="8af76-308">호스팅된  영역 페이지에서 레코드 집합 만들기를 선택하고 **표의** 다음 행 값을 사용하여 레코드를 만든  다음 만들기를 다시 선택하여 해당 레코드를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-308">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="8af76-309">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="8af76-309">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="8af76-310">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8af76-310">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="8af76-311">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8af76-311">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
