---
title: Web.com에서 Microsoft에 대 한 DNS 레코드 만들기
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대 한 DNS 레코드를 Microsoft 용 web.com에 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: ec1d0168fb8a9dfb30d47412146777bc88f90a46
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629254"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a><span data-ttu-id="67ec9-103">Web.com에서 Microsoft에 대 한 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="67ec9-103">Create DNS records at web.com for Microsoft</span></span>

 <span data-ttu-id="67ec9-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="67ec9-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="67ec9-105">Web.com이 DNS 호스팅 공급자 인 경우이 문서의 단계에 따라 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 등에 대 한 DNS 레코드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="67ec9-106">Web.com에서 이러한 레코드를 추가 하 고 나면 도메인이 Microsoft 서비스에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-106">After you add these records at web.com, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="67ec9-107">Microsoft의 웹 사이트에 대 한 호스트 및 DNS에 대 한 자세한 내용은 [microsoft에서 공개 웹 사이트 사용](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="67ec9-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="67ec9-p101">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67ec9-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="67ec9-111">도메인의 NS(이름 서버) 레코드 변경</span><span class="sxs-lookup"><span data-stu-id="67ec9-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="67ec9-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="67ec9-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="67ec9-113">이 절차는 도메인을 구입하고 등록한 도메인 등록 기관에서 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="67ec9-114">Web.com에 등록할 때 web.com **설치** 프로세스를 사용 하 여 도메인을 추가 했습니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-114">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="67ec9-115">Microsoft에서 도메인에 대 한 DNS 레코드를 확인 하 고 만들려면 먼저 이름 서버를 사용 하도록 도메인 등록 기관에서 이름 서버를 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-115">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="67ec9-116">도메인 등록 기관 웹 사이트에서 도메인 이름 서버를 직접 변경하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="67ec9-117">도메인 등록 기관의 웹 사이트에서 도메인의 이름 서버를 편집할 수 있는 영역을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="67ec9-118">다음 표의 값을 사용 하 여 두 개의 이름 서버 레코드를 만들거나 기존 이름 서버 레코드를 해당 값과 일치 하도록 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="67ec9-119">첫 번째 이름 서버</span><span class="sxs-lookup"><span data-stu-id="67ec9-119">First nameserver</span></span>  <br/> |<span data-ttu-id="67ec9-120">Web.com에서 제공 하는 이름 서버 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-120">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="67ec9-121">두 번째 이름 서버</span><span class="sxs-lookup"><span data-stu-id="67ec9-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="67ec9-122">Web.com에서 제공 하는 이름 서버 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-122">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="67ec9-123">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="67ec9-123">You should use at least two name server records.</span></span> <span data-ttu-id="67ec9-124">다른 이름 서버가 나열 되어 있으면 삭제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="67ec9-125">변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="67ec9-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="67ec9-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="67ec9-127">그러면 Microsoft 전자 메일 및 기타 서비스가 모두 도메인에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-127">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="67ec9-128">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="67ec9-128">Add a TXT record for verification</span></span>
<span data-ttu-id="67ec9-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="67ec9-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="67ec9-130">Microsoft에서 도메인을 사용 하기 전에 사용자가 소유 하 고 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-130">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="67ec9-131">도메인 등록 기관에서 계정에 로그인 하 고 DNS 레코드를 만들 수 있는 기능은 Microsoft에 도메인을 소유 하 고 있음을 증명 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-131">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="67ec9-p105">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="67ec9-134">시작 하려면 [이 링크](https://checkout.web.com/manage-it/index.jsp)를 사용 하 여 web.com의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-134">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="67ec9-135">먼저 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-135">Log in first.</span></span>
  
2. <span data-ttu-id="67ec9-136">**계정 관리자** 페이지에서 **내 도메인 이름을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-136">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="67ec9-137">\* \* 관리 \* 내 도메인 \* \* \*에서 **고급 DNS 레코드 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-137">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="67ec9-138">**도메인 이름** 페이지의 **텍스트 (txt 레코드)** 에서 **txt 레코드 편집**을 클릭 하 고 다음 표에서 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-138">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="67ec9-139">**호스트**</span><span class="sxs-lookup"><span data-stu-id="67ec9-139">**Host**</span></span>|<span data-ttu-id="67ec9-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="67ec9-140">**TTL**</span></span>|<span data-ttu-id="67ec9-141">**텍스트**</span><span class="sxs-lookup"><span data-stu-id="67ec9-141">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="67ec9-142">3600</span><span class="sxs-lookup"><span data-stu-id="67ec9-142">3600</span></span>  <br/> |<span data-ttu-id="67ec9-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="67ec9-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="67ec9-144">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-144">**Note:** This is an example.</span></span> <span data-ttu-id="67ec9-145">표에서 특정 **대상 또는 지점** 값을 사용 하 여 여기서 주소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-145">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="67ec9-146">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="67ec9-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="67ec9-147">**계속**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-147">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="67ec9-148">방금 만든 레코드가 인터넷에서 업데이트 될 수 있도록 새 TXT 레코드를 확인 하기 전에 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-148">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="67ec9-149">도메인 등록 기관 사이트에서 레코드를 추가 했으므로 이제 Microsoft로 이동 하 여 레코드를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-149">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="67ec9-150">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-150">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="67ec9-151">I관리 센터에서 \*\* 설정 \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="67ec9-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="67ec9-152">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="67ec9-153">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="67ec9-154">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="67ec9-p108">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67ec9-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="67ec9-158">도메인에 대 한 전자 메일이 Microsoft에 제공 되도록 MX 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-158">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="67ec9-159"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="67ec9-159"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="67ec9-160">시작 하려면 [이 링크](https://checkout.web.com/manage-it/index.jsp)를 사용 하 여 web.com의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-160">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="67ec9-161">먼저 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-161">Log in first.</span></span>
  
2. <span data-ttu-id="67ec9-162">**계정 관리자** 페이지에서 **내 도메인 이름을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-162">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="67ec9-163">\* \* 관리 \* 내 도메인 \* \* \*에서 **고급 DNS 레코드 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-163">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="67ec9-164">**메일 서버 (Mx 레코드)** 에서 **mx 레코드 편집**을 클릭 하 고 다음 표에서 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-164">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="67ec9-165">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="67ec9-165">**Priority**</span></span>|<span data-ttu-id="67ec9-166">**TTL**</span><span class="sxs-lookup"><span data-stu-id="67ec9-166">**TTL**</span></span>|<span data-ttu-id="67ec9-167">**메일 서버**</span><span class="sxs-lookup"><span data-stu-id="67ec9-167">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="67ec9-168">1 </span><span class="sxs-lookup"><span data-stu-id="67ec9-168">1</span></span>  <br/> <span data-ttu-id="67ec9-169">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67ec9-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="67ec9-170">3600</span><span class="sxs-lookup"><span data-stu-id="67ec9-170">3600</span></span>  <br/> |<span data-ttu-id="67ec9-171">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="67ec9-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="67ec9-172">**참고:** Microsoft 계정에서 \* \<도메인 키\> \* 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-172">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="67ec9-173">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="67ec9-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="67ec9-174">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-174">Select **Save**.</span></span>
  
6. <span data-ttu-id="67ec9-175">**Mx 레코드** 구역에 다른 mx 레코드가 나열 되어 있으면 **삭제**아래의 레코드 옆에 있는 확인란을 선택 하 고 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-175">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="67ec9-176">확인 화면에서 **변경 내용 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-176">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="67ec9-177">Microsoft에 필요한 6 개의 CNAME 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-177">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="67ec9-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="67ec9-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="67ec9-179">시작 하려면 [이 링크](https://checkout.web.com/manage-it/index.jsp)를 사용 하 여 web.com의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-179">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="67ec9-180">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-180">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="67ec9-181">**계정 관리자** 페이지에서 **내 도메인 이름을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-181">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="67ec9-182">\* \* 관리 \* 내 도메인 \* \* \*에서 **고급 DNS 레코드 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-182">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="67ec9-183">6개의 CNAME 레코드 중 첫 번째 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="67ec9-184">**호스트 별칭 (Cname 레코드)** 에서 **CNAME 레코드 편집**을 클릭 하 고 다음 표에서 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-184">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="67ec9-185">**별칭**</span><span class="sxs-lookup"><span data-stu-id="67ec9-185">**Alias**</span></span>|<span data-ttu-id="67ec9-186">**TTL**</span><span class="sxs-lookup"><span data-stu-id="67ec9-186">**TTL**</span></span>|<span data-ttu-id="67ec9-187">**호스트 이름 참조**</span><span class="sxs-lookup"><span data-stu-id="67ec9-187">**Refers to Host Name**</span></span>|<span data-ttu-id="67ec9-188">**기타 호스트**</span><span class="sxs-lookup"><span data-stu-id="67ec9-188">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="67ec9-189">autodiscover</span><span class="sxs-lookup"><span data-stu-id="67ec9-189">autodiscover</span></span>  <br/> |<span data-ttu-id="67ec9-190">3600</span><span class="sxs-lookup"><span data-stu-id="67ec9-190">3600</span></span>  <br/> |<span data-ttu-id="67ec9-191">@ (없음)</span><span class="sxs-lookup"><span data-stu-id="67ec9-191">@ (none)</span></span>  <br/> |<span data-ttu-id="67ec9-192">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="67ec9-192">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="67ec9-193">sip</span><span class="sxs-lookup"><span data-stu-id="67ec9-193">sip</span></span>  <br/> |<span data-ttu-id="67ec9-194">3600</span><span class="sxs-lookup"><span data-stu-id="67ec9-194">3600</span></span>  <br/> |<span data-ttu-id="67ec9-195">@ (없음)</span><span class="sxs-lookup"><span data-stu-id="67ec9-195">@ (none)</span></span>  <br/> |<span data-ttu-id="67ec9-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="67ec9-196">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="67ec9-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="67ec9-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="67ec9-198">3600</span><span class="sxs-lookup"><span data-stu-id="67ec9-198">3600</span></span>  <br/> |<span data-ttu-id="67ec9-199">@ (없음)</span><span class="sxs-lookup"><span data-stu-id="67ec9-199">@ (none)</span></span>  <br/> | <span data-ttu-id="67ec9-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="67ec9-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="67ec9-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="67ec9-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="67ec9-202">3600</span><span class="sxs-lookup"><span data-stu-id="67ec9-202">3600</span></span>  <br/> |<span data-ttu-id="67ec9-203">@ (없음)</span><span class="sxs-lookup"><span data-stu-id="67ec9-203">@ (none)</span></span>  <br/> |<span data-ttu-id="67ec9-204">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="67ec9-204">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="67ec9-205">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="67ec9-205">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="67ec9-206">3600</span><span class="sxs-lookup"><span data-stu-id="67ec9-206">3600</span></span>  <br/> |<span data-ttu-id="67ec9-207">@ (없음)</span><span class="sxs-lookup"><span data-stu-id="67ec9-207">@ (none)</span></span>  <br/> |<span data-ttu-id="67ec9-208">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="67ec9-208">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="67ec9-209">msoid</span><span class="sxs-lookup"><span data-stu-id="67ec9-209">msoid</span></span>  <br/> |<span data-ttu-id="67ec9-210">3600</span><span class="sxs-lookup"><span data-stu-id="67ec9-210">3600</span></span>  <br/> |<span data-ttu-id="67ec9-211">@ (없음)</span><span class="sxs-lookup"><span data-stu-id="67ec9-211">@ (none)</span></span>  <br/> |<span data-ttu-id="67ec9-212">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="67ec9-212">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="67ec9-213">**계속**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-213">Select **Continue**.</span></span>
  
6. <span data-ttu-id="67ec9-214">나머지 5개의 CNAME 레코드를 각각 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-214">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="67ec9-215">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="67ec9-215">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="67ec9-216"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="67ec9-216"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="67ec9-217">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-217">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="67ec9-218">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="67ec9-219">도메인에 대 한 SPF 레코드가 이미 있는 경우 Microsoft에 대해 새로 만들지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="67ec9-219">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="67ec9-220">대신, 두 값 집합을 모두 포함 하는 *단일* SPF 레코드가 있도록 현재 레코드에 필수 Microsoft 값을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-220">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="67ec9-221">시작 하려면 [이 링크](https://checkout.web.com/manage-it/index.jsp)를 사용 하 여 web.com의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-221">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="67ec9-222">먼저 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-222">Log in first.</span></span>
    
  
2. <span data-ttu-id="67ec9-223">**계정 관리자** 페이지에서 **내 도메인 이름을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-223">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="67ec9-224">\* \* 관리 \* 내 도메인 \* \* \*에서 **고급 DNS 레코드 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-224">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="67ec9-225">**도메인 이름** 페이지의 **텍스트 (txt 레코드)** 에서 **txt 레코드 편집**을 클릭 하 고 다음 표에서 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-225">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="67ec9-226">**호스트**</span><span class="sxs-lookup"><span data-stu-id="67ec9-226">**Host**</span></span>|<span data-ttu-id="67ec9-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="67ec9-227">**TTL**</span></span>|<span data-ttu-id="67ec9-228">**텍스트**</span><span class="sxs-lookup"><span data-stu-id="67ec9-228">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="67ec9-229">3600</span><span class="sxs-lookup"><span data-stu-id="67ec9-229">3600</span></span>  <br/> |<span data-ttu-id="67ec9-230">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="67ec9-230">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="67ec9-231">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-231">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="67ec9-232">**계속**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-232">Select **Continue**.</span></span>

6. <span data-ttu-id="67ec9-233">**변경 내용 저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-233">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="67ec9-234">Microsoft에 필요한 두 개의 SRV 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-234">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="67ec9-235"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="67ec9-235"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="67ec9-236">Web.com는이 기능을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-236">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="67ec9-237">아래 단계와 현재 web.com GUI (그래픽 사용자 인터페이스) 간의 불일치가 표시 되는 경우 [Web.com 커뮤니티](https://community.web.com.com/)를 활용 하세요.</span><span class="sxs-lookup"><span data-stu-id="67ec9-237">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="67ec9-238">시작 하려면 [이 링크](https://checkout.web.com/manage-it/index.jsp)를 사용 하 여 web.com의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-238">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="67ec9-239">먼저 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-239">Log in first.</span></span>
      
2. <span data-ttu-id="67ec9-240">**계정 관리자** 페이지에서 **내 도메인 이름을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-240">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="67ec9-241">\* \* 관리 \* 내 도메인 \* \* \*에서 **고급 DNS 레코드 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-241">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="67ec9-242">처음 2개의 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-242">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="67ec9-243">**서비스 (Srv 레코드)** 에서 **SRV 레코드 편집**을 클릭 하 고 다음 표에서 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-243">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="67ec9-244">**서비스**</span><span class="sxs-lookup"><span data-stu-id="67ec9-244">**Service**</span></span>|<span data-ttu-id="67ec9-245">**프로토콜**</span><span class="sxs-lookup"><span data-stu-id="67ec9-245">**Protocol**</span></span>|<span data-ttu-id="67ec9-246">**TTL**</span><span class="sxs-lookup"><span data-stu-id="67ec9-246">**TTL**</span></span>|<span data-ttu-id="67ec9-247">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="67ec9-247">**Priority**</span></span>|<span data-ttu-id="67ec9-248">**Weight(가중치)**</span><span class="sxs-lookup"><span data-stu-id="67ec9-248">**Weight**</span></span>|<span data-ttu-id="67ec9-249">**Port(포트)**</span><span class="sxs-lookup"><span data-stu-id="67ec9-249">**Port**</span></span>|<span data-ttu-id="67ec9-250">**대상**</span><span class="sxs-lookup"><span data-stu-id="67ec9-250">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="67ec9-251">_sip</span><span class="sxs-lookup"><span data-stu-id="67ec9-251">_sip</span></span> |<span data-ttu-id="67ec9-252">_tls</span><span class="sxs-lookup"><span data-stu-id="67ec9-252">_tls</span></span> |<span data-ttu-id="67ec9-253">3600</span><span class="sxs-lookup"><span data-stu-id="67ec9-253">3600</span></span> | <span data-ttu-id="67ec9-254">100</span><span class="sxs-lookup"><span data-stu-id="67ec9-254">100</span></span>|<span data-ttu-id="67ec9-255">1 </span><span class="sxs-lookup"><span data-stu-id="67ec9-255">1</span></span> |<span data-ttu-id="67ec9-256">443</span><span class="sxs-lookup"><span data-stu-id="67ec9-256">443</span></span> |<span data-ttu-id="67ec9-257">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="67ec9-257">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="67ec9-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="67ec9-258">_sipfederationtls</span></span> |<span data-ttu-id="67ec9-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="67ec9-259">_tcp</span></span> |<span data-ttu-id="67ec9-260">3600</span><span class="sxs-lookup"><span data-stu-id="67ec9-260">3600</span></span> |<span data-ttu-id="67ec9-261">100</span><span class="sxs-lookup"><span data-stu-id="67ec9-261">100</span></span> |<span data-ttu-id="67ec9-262">1 </span><span class="sxs-lookup"><span data-stu-id="67ec9-262">1</span></span> |<span data-ttu-id="67ec9-263">5061</span><span class="sxs-lookup"><span data-stu-id="67ec9-263">5061</span></span> | <span data-ttu-id="67ec9-264">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="67ec9-264">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="67ec9-265">표의 두 번째 행에서 값을 선택 하 여 다른 SRV 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-265">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="67ec9-266">**계속**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-266">Select **Continue**.</span></span>

7. <span data-ttu-id="67ec9-267">**변경 내용 저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67ec9-267">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="67ec9-p116">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67ec9-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
