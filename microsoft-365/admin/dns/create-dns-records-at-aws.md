---
title: Microsoft의 AWS (Amazon Web Services)에서 DNS 레코드 만들기
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
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: Microsoft의 AWS (Amazon Web Services)에서 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대 한 DNS 레코드를 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 1ce4d47dce2fce177efafade49b78ea706cf14e2
ms.sourcegitcommit: 2399ee6f9bc955cf8f2a76c01fc84c19eb37ff42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2020
ms.locfileid: "43919542"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-microsoft"></a><span data-ttu-id="6aa95-103">Microsoft의 AWS (Amazon Web Services)에서 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="6aa95-103">Create DNS records at Amazon Web Services (AWS) for Microsoft</span></span>

 <span data-ttu-id="6aa95-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="6aa95-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="6aa95-105">AWS이 DNS 호스팅 공급자 인 경우이 문서의 단계에 따라 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 등에 대 한 DNS 레코드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-105">If AWS is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype Online for Business, and so on.</span></span>
  
<span data-ttu-id="6aa95-106">AWS에서 이러한 레코드를 추가 하 고 나면 도메인이 Microsoft 서비스에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-106">After you add these records at AWS, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="6aa95-107">마이크로 sfot을 사용 하는 웹 사이트에 대 한 호스트 및 DNS에 대 한 자세한 내용은 [Microsoft에서 공개 웹 사이트 사용](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6aa95-107">To learn about webhosting and DNS for websites with Microsfot, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6aa95-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="6aa95-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="6aa95-109">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="6aa95-110">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6aa95-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="6aa95-111">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="6aa95-111">Add a TXT record for verification</span></span>
<span data-ttu-id="6aa95-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="6aa95-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="6aa95-p102">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6aa95-p103">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="6aa95-117">시작하려면 [이 링크](https://console.aws.amazon.com/route53/home)를 사용하여 AWS의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="6aa95-118">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="6aa95-119">**리소스** 페이지에서 **호스트 된 영역**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-119">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="6aa95-120">**호스팅된 영역** 페이지의 **Domain Name (도메인 이름** ) 열에서 편집 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-120">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="6aa95-121">**레코드 집합 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-121">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="6aa95-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="6aa95-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="6aa95-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="6aa95-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="6aa95-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="6aa95-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6aa95-126">**이름**</span><span class="sxs-lookup"><span data-stu-id="6aa95-126">**Name**</span></span> <br/> |<span data-ttu-id="6aa95-127">**종류**</span><span class="sxs-lookup"><span data-stu-id="6aa95-127">**Type**</span></span> <br/> |<span data-ttu-id="6aa95-128">**별칭**</span><span class="sxs-lookup"><span data-stu-id="6aa95-128">**Alias**</span></span> <br/> |<span data-ttu-id="6aa95-129">**TTL(초)**</span><span class="sxs-lookup"><span data-stu-id="6aa95-129">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="6aa95-130">**값**</span><span class="sxs-lookup"><span data-stu-id="6aa95-130">**Value**</span></span> <br/> |<span data-ttu-id="6aa95-131">**라우팅 정책**</span><span class="sxs-lookup"><span data-stu-id="6aa95-131">**Routing Policy**</span></span> <br/> |
    |<span data-ttu-id="6aa95-132">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="6aa95-132">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="6aa95-133">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="6aa95-133">TXT - Text</span></span>  <br/> |<span data-ttu-id="6aa95-134">아니요</span><span class="sxs-lookup"><span data-stu-id="6aa95-134">No</span></span>  <br/> |<span data-ttu-id="6aa95-135">300</span><span class="sxs-lookup"><span data-stu-id="6aa95-135">300</span></span>  <br/> |<span data-ttu-id="6aa95-136">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="6aa95-136">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="6aa95-137">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-137">**Note:** This is an example.</span></span> <span data-ttu-id="6aa95-138">여기에는 Microsoft 365의 표에 있는 특정 **주소를 지정할 대상 또는 지점** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-138">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span> [<span data-ttu-id="6aa95-139">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="6aa95-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="6aa95-140">Simple(단순형)</span><span class="sxs-lookup"><span data-stu-id="6aa95-140">Simple</span></span>  <br/> |
   
6. <span data-ttu-id="6aa95-141">**만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-141">Select **Create**.</span></span>
    
7. <span data-ttu-id="6aa95-142">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-142">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="6aa95-143">도메인 등록 기관 사이트에서 레코드를 추가 했으므로 이제 Microsoft로 이동 하 여 레코드 검색을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-143">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="6aa95-144">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-144">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="6aa95-145">Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-145">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="6aa95-146">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-146">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="6aa95-147">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-147">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="6aa95-148">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-148">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6aa95-149">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="6aa95-149">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="6aa95-150">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-150">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="6aa95-151">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6aa95-151">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a><span data-ttu-id="6aa95-152">도메인에 대 한 전자 메일이 Microsoft 365에 제공 되도록 MX 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-152">Add an MX record so email for your domain will come to Microsoft 365</span></span>
<span data-ttu-id="6aa95-153"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="6aa95-153"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="6aa95-p108">시작하려면 [이 링크](https://console.aws.amazon.com/route53/home)를 사용하여 AWS의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-p108">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="6aa95-156">**리소스** 페이지에서 **호스트 된 영역**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-156">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="6aa95-157">**호스팅된 영역** 페이지의 **Domain Name (도메인 이름** ) 열에서 편집 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-157">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="6aa95-158">**레코드 집합 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-158">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="6aa95-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="6aa95-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="6aa95-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="6aa95-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="6aa95-161">**이름**</span><span class="sxs-lookup"><span data-stu-id="6aa95-161">**Name**</span></span>|<span data-ttu-id="6aa95-162">**종류**</span><span class="sxs-lookup"><span data-stu-id="6aa95-162">**Type**</span></span>|<span data-ttu-id="6aa95-163">**별칭**</span><span class="sxs-lookup"><span data-stu-id="6aa95-163">**Alias**</span></span>|<span data-ttu-id="6aa95-164">**TTL(초)**</span><span class="sxs-lookup"><span data-stu-id="6aa95-164">**TTL (Seconds)**</span></span>|<span data-ttu-id="6aa95-165">**값**</span><span class="sxs-lookup"><span data-stu-id="6aa95-165">**Value**</span></span>|<span data-ttu-id="6aa95-166">**라우팅 정책**</span><span class="sxs-lookup"><span data-stu-id="6aa95-166">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6aa95-167">(이 필드는 비워 둡니다.)</span><span class="sxs-lookup"><span data-stu-id="6aa95-167">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="6aa95-168">MX - Mail Exchanger(MX - 메일 교환기)</span><span class="sxs-lookup"><span data-stu-id="6aa95-168">MX - Mail exchange</span></span>  <br/> |<span data-ttu-id="6aa95-169">아니요</span><span class="sxs-lookup"><span data-stu-id="6aa95-169">No</span></span>  <br/> |<span data-ttu-id="6aa95-170">300</span><span class="sxs-lookup"><span data-stu-id="6aa95-170">300</span></span>  <br/> |<span data-ttu-id="6aa95-171">0  *\<도메인 키\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="6aa95-171">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="6aa95-p109">0은 MX 우선 순위 값입니다. 이 값을 MX 값 시작 부분에 추가하고 나머지 값과 공백으로 구분합니다.  </span><span class="sxs-lookup"><span data-stu-id="6aa95-p109">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="6aa95-174">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="6aa95-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="6aa95-175">**참고:** \<Microsoft 365 계정에서 *도메인 키* \> 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-175">**Note:** Get your \<*domain-key*\> from your Microsoft 365 account.</span></span> [<span data-ttu-id="6aa95-176">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="6aa95-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="6aa95-177">Simple(단순형)</span><span class="sxs-lookup"><span data-stu-id="6aa95-177">Simple</span></span>  <br/> |
       
    ![AWS-BP-구성-2-1](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. <span data-ttu-id="6aa95-179">**만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-179">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. <span data-ttu-id="6aa95-181">다른 MX 레코드가 있으면 해당 레코드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-181">If there are any other MX records, remove them.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="6aa95-182">AWS에서는 MX 레코드를 여러 레코드가 포함될 수 있는 한 집합으로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-182">AWS stores MX records as a set that may contain multiple records.</span></span> <span data-ttu-id="6aa95-183">**레코드 집합 삭제** **를 선택 하면** 방금 추가한 MX 레코드를 포함 하 여 모두 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-183">**DO NOT** select **Delete Record Set**, as this will delete all of your MX records, including the one you just added.</span></span> <span data-ttu-id="6aa95-184">대신 다음 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-184">Use the following instructions instead.</span></span> 
  
    <span data-ttu-id="6aa95-185">먼저 MX 레코드 집합을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-185">First, select the MX record set.</span></span>
    
    ![AWS-BP-Configure-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    <span data-ttu-id="6aa95-187">다음으로, **Edit Record Set(레코드 집합 편집)** 영역의 **Value(값)** 상자에서 항목을 선택한 다음 키보드의 **Delete** 키를 눌러 오래된 각 MX 레코드를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-187">Next, in the **Edit Record Set** area, delete each obsolete MX record by selecting the entry in the **Value** box and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![AWS-BP-Configure-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. <span data-ttu-id="6aa95-189">**레코드 집합 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-189">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="6aa95-191">Microsoft 365에 필요한 5 개의 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="6aa95-191">Add the five CNAME records that are required for Microsoft 365</span></span>
<span data-ttu-id="6aa95-192"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="6aa95-192"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="6aa95-p112">시작하려면 [이 링크](https://console.aws.amazon.com/route53/home)를 사용하여 AWS의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-p112">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="6aa95-195">**리소스** 페이지에서 **호스트 된 영역**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-195">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="6aa95-196">**호스팅된 영역** 페이지의 **Domain Name (도메인 이름** ) 열에서 편집 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-196">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="6aa95-197">**레코드 집합 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-197">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="6aa95-198">첫 번째 CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-198">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="6aa95-199">**Create Record Set(레코드 집합 만들기)** 영역의 새 레코드용 상자에 다음 표의 첫 번째 행에 있는 값을 입력하거나 복사하여 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-199">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="6aa95-200">(드롭다운 목록에서 **Type**(종류) 및 **Routing Policy**(라우팅 정책) 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="6aa95-200">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="6aa95-201">**이름**</span><span class="sxs-lookup"><span data-stu-id="6aa95-201">**Name**</span></span>|<span data-ttu-id="6aa95-202">**종류**</span><span class="sxs-lookup"><span data-stu-id="6aa95-202">**Type**</span></span>|<span data-ttu-id="6aa95-203">**별칭**</span><span class="sxs-lookup"><span data-stu-id="6aa95-203">**Alias**</span></span>|<span data-ttu-id="6aa95-204">**TTL(초)**</span><span class="sxs-lookup"><span data-stu-id="6aa95-204">**TTL (Seconds)**</span></span>|<span data-ttu-id="6aa95-205">**값**</span><span class="sxs-lookup"><span data-stu-id="6aa95-205">**Value**</span></span>|<span data-ttu-id="6aa95-206">**라우팅 정책**</span><span class="sxs-lookup"><span data-stu-id="6aa95-206">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6aa95-207">autodiscover</span><span class="sxs-lookup"><span data-stu-id="6aa95-207">autodiscover</span></span>  <br/> |<span data-ttu-id="6aa95-208">CNAME - Canonical name(CNAME - 정식 이름)</span><span class="sxs-lookup"><span data-stu-id="6aa95-208">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="6aa95-209">No(아니요)</span><span class="sxs-lookup"><span data-stu-id="6aa95-209">No</span></span>  <br/> |<span data-ttu-id="6aa95-210">300</span><span class="sxs-lookup"><span data-stu-id="6aa95-210">300</span></span>  <br/> |<span data-ttu-id="6aa95-211">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="6aa95-211">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="6aa95-212">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="6aa95-212">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="6aa95-213">Simple(단순형)</span><span class="sxs-lookup"><span data-stu-id="6aa95-213">Simple</span></span>  <br/> |
    |<span data-ttu-id="6aa95-214">sip</span><span class="sxs-lookup"><span data-stu-id="6aa95-214">sip</span></span>  <br/> |<span data-ttu-id="6aa95-215">CNAME - Canonical name(CNAME - 정식 이름)</span><span class="sxs-lookup"><span data-stu-id="6aa95-215">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="6aa95-216">No(아니요)</span><span class="sxs-lookup"><span data-stu-id="6aa95-216">No</span></span>  <br/> |<span data-ttu-id="6aa95-217">300</span><span class="sxs-lookup"><span data-stu-id="6aa95-217">300</span></span>  <br/> |<span data-ttu-id="6aa95-218">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6aa95-218">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="6aa95-219">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="6aa95-219">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="6aa95-220">Simple(단순형)</span><span class="sxs-lookup"><span data-stu-id="6aa95-220">Simple</span></span>  <br/> |
    |<span data-ttu-id="6aa95-221">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="6aa95-221">lyncdiscover</span></span>  <br/> |<span data-ttu-id="6aa95-222">CNAME - Canonical name(CNAME - 정식 이름)</span><span class="sxs-lookup"><span data-stu-id="6aa95-222">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="6aa95-223">No(아니요)</span><span class="sxs-lookup"><span data-stu-id="6aa95-223">No</span></span>  <br/> |<span data-ttu-id="6aa95-224">300</span><span class="sxs-lookup"><span data-stu-id="6aa95-224">300</span></span>  <br/> |<span data-ttu-id="6aa95-225">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6aa95-225">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="6aa95-226">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="6aa95-226">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="6aa95-227">Simple(단순형)</span><span class="sxs-lookup"><span data-stu-id="6aa95-227">Simple</span></span>  <br/> |
    |<span data-ttu-id="6aa95-228">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="6aa95-228">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="6aa95-229">CNAME - Canonical name(CNAME - 정식 이름)</span><span class="sxs-lookup"><span data-stu-id="6aa95-229">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="6aa95-230">No(아니요)</span><span class="sxs-lookup"><span data-stu-id="6aa95-230">No</span></span>  <br/> |<span data-ttu-id="6aa95-231">300</span><span class="sxs-lookup"><span data-stu-id="6aa95-231">300</span></span>  <br/> |<span data-ttu-id="6aa95-232">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="6aa95-232">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="6aa95-233">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="6aa95-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="6aa95-234">Simple(기본)</span><span class="sxs-lookup"><span data-stu-id="6aa95-234">Simple</span></span>  <br/> |
    |<span data-ttu-id="6aa95-235">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="6aa95-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="6aa95-236">CNAME - Canonical name(CNAME - 정식 이름)</span><span class="sxs-lookup"><span data-stu-id="6aa95-236">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="6aa95-237">No(아니요)</span><span class="sxs-lookup"><span data-stu-id="6aa95-237">No</span></span>  <br/> |<span data-ttu-id="6aa95-238">300</span><span class="sxs-lookup"><span data-stu-id="6aa95-238">300</span></span>  <br/> |<span data-ttu-id="6aa95-239">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="6aa95-239">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="6aa95-240">**이 값은 마침표(.)로 끝나야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="6aa95-240">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="6aa95-241">Simple(단순형)</span><span class="sxs-lookup"><span data-stu-id="6aa95-241">Simple</span></span>  <br/> |
   
    ![AWS-BP-구성-3-1](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. <span data-ttu-id="6aa95-243">**만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-243">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. <span data-ttu-id="6aa95-245">나머지 4개의 CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-245">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="6aa95-246">**호스팅된 영역** 페이지에서 **레코드 집합 만들기**를 선택 하 고 표의 다음 행에 있는 값을 사용 하 여 레코드를 만든 다음 다시 **만들기** 를 선택 하 여 해당 레코드를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-246">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
    <span data-ttu-id="6aa95-247">5 개의 CNAME 레코드를 모두 만들 때까지이 프로세스를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-247">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="6aa95-248">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="6aa95-248">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="6aa95-249"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="6aa95-249"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="6aa95-250">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-250">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="6aa95-251">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-251">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="6aa95-252">도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="6aa95-252">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="6aa95-253">대신, 두 값 집합을 모두 포함 하는 *단일* SPF 레코드가 있도록 현재 레코드에 필수 Microsoft 값을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-253">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="6aa95-254">예제가 필요하세요?</span><span class="sxs-lookup"><span data-stu-id="6aa95-254">Need examples?</span></span> <span data-ttu-id="6aa95-255">[Microsoft에 대한 외부 Domain Name System 레코드](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6aa95-255">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="6aa95-256">SPF 레코드의 유효성을 검사 하기 위해 이러한[spf 유효성 검사 도구](../setup/domains-faq.md)중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-256">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="6aa95-257">시작하려면 [이 링크](https://console.aws.amazon.com/route53/home)를 사용하여 AWS의 도메인 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-257">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="6aa95-258">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-258">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="6aa95-259">**리소스** 페이지에서 **호스트 된 영역**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-259">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="6aa95-260">**호스팅된 영역** 페이지의 **Domain Name (도메인 이름** ) 열에서 편집 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-260">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="6aa95-261">**TXT** 레코드 집합을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-261">Select the **TXT** record set.</span></span> 
    
    ![AWS-BP-Configure-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. <span data-ttu-id="6aa95-p115">**레코드 집합 편집** 영역에서 기존 레코드의 **값:** 상자에 있는 현재 항목의 맨 끝에서 키보드의 Enter를 눌러 새 줄을 만든 다음, 이 새 줄에서(기존 값 아래) 다음 표의 값을 입력하거나 복사하여 붙여넣습니다. (표 아래 그림의 예를 참조할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="6aa95-p115">In the **Edit Record Set** area, at the end of the current entry in the **Value:** box for the existing record, press Enter on your keyboard to create a new line; and then, on that new line (under the existing value), type or copy and paste the value from the following table. (You can see an example in the illustration below the table.)</span></span> 
    
    |<span data-ttu-id="6aa95-265">**값:**</span><span class="sxs-lookup"><span data-stu-id="6aa95-265">**Value:**</span></span>|
    |:-----|
    |<span data-ttu-id="6aa95-266">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="6aa95-266">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="6aa95-p116">(화면 지침에 필요한 물음표가 자동으로 제공됩니다. 직접 입력할 필요가 없습니다.)  </span><span class="sxs-lookup"><span data-stu-id="6aa95-p116">(The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.)  </span></span><br/> <span data-ttu-id="6aa95-269">\*\*참고: \*\* 모든 간격이 올바르게 유지되도록 이 항목을 복사하여 붙여넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![AWS-BP-구성-4-2](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. <span data-ttu-id="6aa95-271">**레코드 집합 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-271">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="6aa95-273">Microsoft 365에 필요한 2 개의 SRV 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-273">Add the two SRV records that are required for Microsoft 365</span></span>
<span data-ttu-id="6aa95-274"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="6aa95-274"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="6aa95-p117">시작하려면 [이 링크](https://console.aws.amazon.com/route53/home)를 사용하여 AWS의 도메인 페이지로 이동합니다. 먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-p117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="6aa95-277">**리소스** 페이지에서 **호스트 된 영역**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-277">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="6aa95-278">**호스팅된 영역** 페이지의 **Domain Name (도메인 이름** ) 열에서 편집 하려는 도메인의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-278">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="6aa95-279">**레코드 집합 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-279">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="6aa95-280">첫 번째 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-280">Add the first SRV record:</span></span>
    
    <span data-ttu-id="6aa95-281">**Create Record Set(레코드 집합 만들기)** 영역의 새 레코드용 상자에 다음 표의 첫 번째 행에 있는 값을 입력하거나 복사하여 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-281">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="6aa95-282">(드롭다운 목록에서 **Type**(종류) 및 **Routing Policy**(라우팅 정책) 값을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="6aa95-282">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="6aa95-283">**이름**</span><span class="sxs-lookup"><span data-stu-id="6aa95-283">**Name**</span></span>|<span data-ttu-id="6aa95-284">**종류**</span><span class="sxs-lookup"><span data-stu-id="6aa95-284">**Type**</span></span>|<span data-ttu-id="6aa95-285">**별칭**</span><span class="sxs-lookup"><span data-stu-id="6aa95-285">**Alias**</span></span>|<span data-ttu-id="6aa95-286">**TTL(초)**</span><span class="sxs-lookup"><span data-stu-id="6aa95-286">**TTL (Seconds)**</span></span>|<span data-ttu-id="6aa95-287">**값**</span><span class="sxs-lookup"><span data-stu-id="6aa95-287">**Value**</span></span>|<span data-ttu-id="6aa95-288">**라우팅 정책**</span><span class="sxs-lookup"><span data-stu-id="6aa95-288">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6aa95-289">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="6aa95-289">_sip._tls</span></span>|<span data-ttu-id="6aa95-290">SRV - Service locator(SRV - 서비스 로케이터)</span><span class="sxs-lookup"><span data-stu-id="6aa95-290">SRV - Service locator</span></span>|<span data-ttu-id="6aa95-291">아니요</span><span class="sxs-lookup"><span data-stu-id="6aa95-291">No</span></span>|<span data-ttu-id="6aa95-292">300</span><span class="sxs-lookup"><span data-stu-id="6aa95-292">300</span></span>|<span data-ttu-id="6aa95-293">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="6aa95-293">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="6aa95-294">**이 값은 마침표 (.)로 끝나야 합니다.**></span><span class="sxs-lookup"><span data-stu-id="6aa95-294">**This value MUST end with a period (.)**></span></span><br> <span data-ttu-id="6aa95-295">\*\*참고: \*\* 모든 간격이 올바르게 유지되도록 이 항목을 복사하여 붙여넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="6aa95-296">Simple(단순형)</span><span class="sxs-lookup"><span data-stu-id="6aa95-296">Simple</span></span>|
    |<span data-ttu-id="6aa95-297">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="6aa95-297">_sipfederationtls._tcp</span></span>|<span data-ttu-id="6aa95-298">SRV - Service locator(SRV - 서비스 로케이터)</span><span class="sxs-lookup"><span data-stu-id="6aa95-298">SRV - Service locator</span></span>|<span data-ttu-id="6aa95-299">아니요</span><span class="sxs-lookup"><span data-stu-id="6aa95-299">No</span></span>|<span data-ttu-id="6aa95-300">300</span><span class="sxs-lookup"><span data-stu-id="6aa95-300">300</span></span>|<span data-ttu-id="6aa95-301">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="6aa95-301">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="6aa95-302">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="6aa95-302">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="6aa95-303">\*\*참고: \*\* 모든 간격이 올바르게 유지되도록 이 항목을 복사하여 붙여넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-303">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="6aa95-304">Simple(단순형)</span><span class="sxs-lookup"><span data-stu-id="6aa95-304">Simple</span></span>|
   
    ![AWS-BP-구성-5-1](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. <span data-ttu-id="6aa95-306">**만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-306">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. <span data-ttu-id="6aa95-308">다른 SRV 레코드를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="6aa95-308">To add the other SRV record:</span></span>
    
    <span data-ttu-id="6aa95-309">**호스팅된 영역** 페이지에서 **레코드 집합 만들기**를 선택 하 고 표의 다음 행에 있는 값을 사용 하 여 레코드를 만든 다음 다시 **만들기** 를 선택 하 여 해당 레코드를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-309">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="6aa95-310">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="6aa95-310">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="6aa95-311">그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa95-311">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="6aa95-312">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제가 발생하는 경우 [도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결하기](../get-help-with-domains/find-and-fix-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6aa95-312">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
