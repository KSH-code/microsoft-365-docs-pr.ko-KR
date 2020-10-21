---
title: Azure DNS 영역에 대 한 DNS 레코드 만들기
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
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대해 Microsoft의 Azure DNS 영역에 대 한 DNS 레코드를 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 40fadb81ebd0ae5385bbbdad727b1c579142b227
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645674"
---
# <a name="create-dns-records-for-azure-dns-zones"></a><span data-ttu-id="5f8ef-103">Azure DNS 영역에 대 한 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="5f8ef-103">Create DNS records for Azure DNS zones</span></span>

 <span data-ttu-id="5f8ef-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="5f8ef-105">Azure가 DNS 호스팅 공급자 이면이 문서에 나와 있는 단계에 따라 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 등에 대 한 DNS 레코드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-105">If Azure is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="5f8ef-106">다음은 추가할 기본 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="5f8ef-107">도메인의 NS(이름 서버) 레코드 변경</span><span class="sxs-lookup"><span data-stu-id="5f8ef-107">Change your domain's nameserver (NS) records</span></span>](#change-your-domains-nameserver-ns-records)
    
- [<span data-ttu-id="5f8ef-108">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="5f8ef-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)

- [<span data-ttu-id="5f8ef-109">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="5f8ef-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="5f8ef-110">Microsoft에 필요한 4 개의 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="5f8ef-110">Add the four CNAME records that are required for Microsoft</span></span>](#add-the-four-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="5f8ef-111">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="5f8ef-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="5f8ef-112">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="5f8ef-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="5f8ef-113">Azure에서 이러한 레코드를 추가 하 고 나면 도메인이 Microsoft 서비스에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-113">After you add these records at Azure, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5f8ef-p101">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="5f8ef-117">도메인의 NS(이름 서버) 레코드 변경</span><span class="sxs-lookup"><span data-stu-id="5f8ef-117">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="5f8ef-118"><a name="BKMK_NS"> </a></span><span class="sxs-lookup"><span data-stu-id="5f8ef-118"><a name="BKMK_NS"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f8ef-119">이 절차는 도메인을 구입하고 등록한 도메인 등록 기관에서 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-119">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="5f8ef-120">Azure에 등록할 때 DNS 영역 내에 리소스 그룹을 만든 다음 해당 리소스 그룹에 도메인 이름을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-120">When you signed up for Azure, you created a resource group within a DNS zone, and then assigned your domain name to that resource group.</span></span> <span data-ttu-id="5f8ef-121">해당 도메인 이름은 외부 도메인 등록자에 등록 됩니다. Azure는 도메인 등록 서비스를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-121">That domain name is registered to an external domain registrar; Azure does not offer domain registration services.</span></span>
  
<span data-ttu-id="5f8ef-122">Microsoft에서 도메인에 대 한 DNS 레코드를 확인 하 고 만들려면 먼저 도메인 등록 기관에서 이름 서버를 변경 하 여 리소스 그룹에 할당 된 Azure 이름 서버을 사용 하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-122">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use the Azure nameservers assigned to your resource group.</span></span>
  
<span data-ttu-id="5f8ef-123">도메인 등록 기관 웹 사이트에서 도메인 이름 서버를 직접 변경하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-123">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="5f8ef-124">도메인 등록 기관의 웹 사이트에서 도메인의 이름 서버를 편집할 수 있는 영역을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-124">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="5f8ef-125">다음 표의 값을 사용 하 여 두 개의 이름 서버 레코드를 만들거나 기존 이름 서버 레코드를 해당 값과 일치 하도록 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-125">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span> <span data-ttu-id="5f8ef-126">Azure 할당 된 이름 서버의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-126">An example of Azure assigned nameservers is shown below.</span></span>
    


<span data-ttu-id="5f8ef-127">**첫 번째 이름 서버:** Azure에서 할당 된 이름 서버 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-127">**First nameserver:** Use the name server value assigned by Azure.</span></span>  
<span data-ttu-id="5f8ef-128">**두 번째** 이름 서버: Azure에서 할당 된 이름 서버 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-128">**Second nameserver:** Use the name server value assigned by Azure.</span></span>  

![Redelegate-1-1](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> <span data-ttu-id="5f8ef-130">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-130">You should use at least two name server records.</span></span> <span data-ttu-id="5f8ef-131">도메인 등록 기관의 웹 사이트에 다른 이름 서버가 나열 된 경우 해당 서버를 삭제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-131">If there are any other name servers listed at your domain registrar's website, you should delete them.</span></span> 
  
3. <span data-ttu-id="5f8ef-132">변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-132">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5f8ef-133">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-133">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="5f8ef-134">그러면 Microsoft 전자 메일 및 기타 서비스가 모두 도메인에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-134">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="5f8ef-135">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="5f8ef-135">Add a TXT record for verification</span></span>
<span data-ttu-id="5f8ef-136"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="5f8ef-136"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="5f8ef-p106">Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-p106">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5f8ef-p107">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-p107">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="5f8ef-141">시작 하려면 [이 링크](https://portal.azure.com )를 사용 하 여 Azure의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-141">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="5f8ef-142">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-142">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-구성-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="5f8ef-144">**대시보드** 페이지의 **검색 표시줄** 을 사용 하 여 **DNS 영역**을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-144">Using the **search bar** on the **Dashboard** page, type in **DNS zones**.</span></span> <span data-ttu-id="5f8ef-145">결과 표시의 **서비스** 부분 아래에서 **DNS 영역** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-145">In the results display, select **DNS zones** under the **Services** portion.</span></span> <span data-ttu-id="5f8ef-146">리디렉션된 후에는 업데이트할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-146">Once you've been redirected, select the domain that you want to update.</span></span>
    
    ![Azure-BP-구성-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="5f8ef-148">도메인의 **설정** 페이지에 있는 **DNS 영역** 에서 **+ 레코드 집합**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-148">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-구성-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="5f8ef-150">**레코드 집합 추가** 영역의 새 레코드 집합에 대 한 상자에서 다음 표의 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-150">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="5f8ef-151">(드롭다운 목록에서 **Type (종류** ) 및 **TTL 단위** 값을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="5f8ef-151">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="5f8ef-152">**이름**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-152">**Name**</span></span>|<span data-ttu-id="5f8ef-153">**Type(종류)**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-153">**Type**</span></span>|<span data-ttu-id="5f8ef-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-154">**TTL**</span></span>|<span data-ttu-id="5f8ef-155">**TTL 단위**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-155">**TTL unit**</span></span>|<span data-ttu-id="5f8ef-156">**값**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-156">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="5f8ef-157">TXT</span><span class="sxs-lookup"><span data-stu-id="5f8ef-157">TXT</span></span>  <br/> |<span data-ttu-id="5f8ef-158">1 </span><span class="sxs-lookup"><span data-stu-id="5f8ef-158">1</span></span>  <br/> |<span data-ttu-id="5f8ef-159">시간</span><span class="sxs-lookup"><span data-stu-id="5f8ef-159">Hours</span></span>  <br/> |<span data-ttu-id="5f8ef-160">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="5f8ef-160">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="5f8ef-161">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-161">**Note:** This is an example.</span></span> <span data-ttu-id="5f8ef-162">여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-162">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="5f8ef-163">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="5f8ef-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Azure-BP-Verify-1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. <span data-ttu-id="5f8ef-165">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-165">Select **OK**.</span></span>
  
6. <span data-ttu-id="5f8ef-166">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-166">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="5f8ef-167">이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-167">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="5f8ef-168">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-168">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="5f8ef-169">I관리 센터에서 \*\* 설정 \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-169">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="5f8ef-170">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-170">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="5f8ef-171">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-171">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="5f8ef-172">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-172">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="5f8ef-p111">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-p111">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="5f8ef-176">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="5f8ef-176">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="5f8ef-177"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="5f8ef-177"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="5f8ef-178">시작 하려면 [이 링크](https://portal.azure.com )를 사용 하 여 Azure의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-178">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="5f8ef-179">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-179">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-구성-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="5f8ef-181">**대시보드** 페이지의 **모든 리소스** 영역에서 업데이트할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-181">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-구성-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="5f8ef-183">도메인의 **설정** 페이지에 있는 **DNS 영역** 에서 **+ 레코드 집합**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-183">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-구성-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="5f8ef-185">**레코드 집합 추가** 영역의 새 레코드 집합에 대 한 상자에서 다음 표의 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-185">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="5f8ef-186">(드롭다운 목록에서 **Type (종류** ) 및 **TTL 단위** 값을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="5f8ef-186">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="5f8ef-187">**이름**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-187">**Name**</span></span>|<span data-ttu-id="5f8ef-188">**Type(종류)**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-188">**Type**</span></span>|<span data-ttu-id="5f8ef-189">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-189">**TTL**</span></span>|<span data-ttu-id="5f8ef-190">**TTL 단위**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-190">**TTL unit**</span></span>|<span data-ttu-id="5f8ef-191">**기본 설정**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-191">**Preference**</span></span>|<span data-ttu-id="5f8ef-192">**메일 교환**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-192">**Mail Exchange**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="5f8ef-193">MX</span><span class="sxs-lookup"><span data-stu-id="5f8ef-193">MX</span></span>  <br/> |<span data-ttu-id="5f8ef-194">1 </span><span class="sxs-lookup"><span data-stu-id="5f8ef-194">1</span></span>  <br/> |<span data-ttu-id="5f8ef-195">시간</span><span class="sxs-lookup"><span data-stu-id="5f8ef-195">Hours</span></span>  <br/> |<span data-ttu-id="5f8ef-196">10  </span><span class="sxs-lookup"><span data-stu-id="5f8ef-196">10</span></span>  <br/> <span data-ttu-id="5f8ef-197">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-197">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="5f8ef-198">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5f8ef-198">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="5f8ef-199">**참고:**  *\<domain-key\>*  Microsoft 계정에서를 다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-199">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="5f8ef-200">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="5f8ef-200">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Azure-BP-구성-2-1](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. <span data-ttu-id="5f8ef-202">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-202">Select **OK**.</span></span>
    
    ![Azure-BP-구성-2-2](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. <span data-ttu-id="5f8ef-204">**Mx 레코드** 구역에 다른 mx 레코드가 나열 되어 있으면 해당 레코드를 삭제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-204">If there are any other MX records listed in the **MX Records** section, you must delete them.</span></span> 
    
    <span data-ttu-id="5f8ef-205">먼저 **DNS 영역** 에서 **MX 레코드 집합**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-205">First, in the **DNS zone** area, select the **MX Record set**.</span></span>
    
    ![Azure-BP-구성-2-3](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    <span data-ttu-id="5f8ef-207">그런 다음 삭제 하려는 MX 레코드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-207">Next, select the MX record you want to delete.</span></span>
    
    ![Azure-BP-구성-2-4](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. <span data-ttu-id="5f8ef-209">상황에 **맞는 메뉴 (...)** 를 선택한 다음 **제거**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-209">Select the **Context menu (…)**, and then choose **Remove**.</span></span>
    
    ![Azure-BP-구성-2-5](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. <span data-ttu-id="5f8ef-211">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-211">Select **Save**.</span></span>
    
    ![Azure-BP-구성-2-6](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="5f8ef-213">Microsoft에 필요한 4 개의 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="5f8ef-213">Add the four CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="5f8ef-214"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="5f8ef-214"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="5f8ef-215">시작 하려면 [이 링크](https://portal.azure.com )를 사용 하 여 Azure의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-215">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="5f8ef-216">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-216">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-구성-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="5f8ef-218">**대시보드** 페이지의 **모든 리소스** 영역에서 업데이트할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-218">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-구성-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="5f8ef-220">도메인의 **설정** 페이지에 있는 **DNS 영역** 에서 **+ 레코드 집합**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-220">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-구성-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="5f8ef-222">4 개의 CNAME 레코드 중 처음 일부를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-222">Add the first of the four CNAME records.</span></span>
    
    <span data-ttu-id="5f8ef-223">**레코드 집합 추가** 영역의 새 레코드 집합 용 상자에 다음 표에 있는 첫 번째 행의 값을 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-223">In the **Add record set** area, in the boxes for the new record set, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="5f8ef-224">(드롭다운 목록에서 **Type (종류** ) 및 **TTL 단위** 값을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="5f8ef-224">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="5f8ef-225">**이름**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-225">**Name**</span></span>|<span data-ttu-id="5f8ef-226">**Type(종류)**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-226">**Type**</span></span>|<span data-ttu-id="5f8ef-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-227">**TTL**</span></span>|<span data-ttu-id="5f8ef-228">**TTL 단위**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-228">**TTL unit**</span></span>|<span data-ttu-id="5f8ef-229">**별칭**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-229">**Alias**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5f8ef-230">autodiscover</span><span class="sxs-lookup"><span data-stu-id="5f8ef-230">autodiscover</span></span>  <br/> |<span data-ttu-id="5f8ef-231">CNAME</span><span class="sxs-lookup"><span data-stu-id="5f8ef-231">CNAME</span></span>  <br/> |<span data-ttu-id="5f8ef-232">1 </span><span class="sxs-lookup"><span data-stu-id="5f8ef-232">1</span></span>  <br/> |<span data-ttu-id="5f8ef-233">시간</span><span class="sxs-lookup"><span data-stu-id="5f8ef-233">Hours</span></span>  <br/> |<span data-ttu-id="5f8ef-234">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5f8ef-234">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="5f8ef-235">sip</span><span class="sxs-lookup"><span data-stu-id="5f8ef-235">sip</span></span>  <br/> |<span data-ttu-id="5f8ef-236">CNAME</span><span class="sxs-lookup"><span data-stu-id="5f8ef-236">CNAME</span></span>  <br/> |<span data-ttu-id="5f8ef-237">1 </span><span class="sxs-lookup"><span data-stu-id="5f8ef-237">1</span></span>  <br/> |<span data-ttu-id="5f8ef-238">시간</span><span class="sxs-lookup"><span data-stu-id="5f8ef-238">Hours</span></span>  <br/> |<span data-ttu-id="5f8ef-239">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5f8ef-239">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="5f8ef-240">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="5f8ef-240">lyncdiscover</span></span>  <br/> |<span data-ttu-id="5f8ef-241">CNAME</span><span class="sxs-lookup"><span data-stu-id="5f8ef-241">CNAME</span></span>  <br/> |<span data-ttu-id="5f8ef-242">1 </span><span class="sxs-lookup"><span data-stu-id="5f8ef-242">1</span></span>  <br/> |<span data-ttu-id="5f8ef-243">시간</span><span class="sxs-lookup"><span data-stu-id="5f8ef-243">Hours</span></span>  <br/> |<span data-ttu-id="5f8ef-244">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5f8ef-244">webdir.online.lync.com</span></span>  <br/> |
    
   
    ![Azure-BP-구성-3-1](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. <span data-ttu-id="5f8ef-246">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-246">Select **OK**.</span></span>
    
    ![Azure-BP-구성-3-2](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. <span data-ttu-id="5f8ef-248">나머지 3 개의 CNAME 레코드를 각각 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-248">Add each of the other three CNAME records.</span></span>
    
    <span data-ttu-id="5f8ef-249">**DNS 영역** 영역에서 **+ 레코드 집합**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-249">In the **DNS zone** area, select **+ Record set**.</span></span> <span data-ttu-id="5f8ef-250">그런 다음 빈 레코드 집합에서 표의 다음 행 값을 사용 하 여 레코드를 만들고 **확인** 을 선택 하 여 해당 레코드를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-250">Then, in the empty record set, create a record by using the values from the next row in the table, and again select **OK** to complete that record.</span></span> 
    
    <span data-ttu-id="5f8ef-251">4 개의 CNAME 레코드를 모두 만들 때까지이 프로세스를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-251">Repeat this process until you have created all four CNAME records.</span></span>
    
7.  <span data-ttu-id="5f8ef-252">반드시 MDM에 대 한 2 개의 CNAME 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-252">(Optional) Add 2 CNAME records for MDM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f8ef-253">Microsoft 용 MDM (모바일 장치 관리)이 있는 경우 두 개의 CNAME 레코드를 추가로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-253">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="5f8ef-254">다른 4개의 CNAME 레코드를 만드는 데 사용한 절차를 따르되 다음 표의 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="5f8ef-255">(MDM이 없는 경우에는이 단계를 건너뛰어도 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="5f8ef-255">(If you do not have MDM, you can skip this step.)</span></span> 
  
|<span data-ttu-id="5f8ef-256">**이름**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-256">**Name**</span></span>|<span data-ttu-id="5f8ef-257">**Type(종류)**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-257">**Type**</span></span>|<span data-ttu-id="5f8ef-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-258">**TTL**</span></span>|<span data-ttu-id="5f8ef-259">**TTL 단위**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-259">**TTL unit**</span></span>|<span data-ttu-id="5f8ef-260">**별칭**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-260">**Alias**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5f8ef-261">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="5f8ef-261">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="5f8ef-262">CNAME</span><span class="sxs-lookup"><span data-stu-id="5f8ef-262">CNAME</span></span>  <br/> |<span data-ttu-id="5f8ef-263">1 </span><span class="sxs-lookup"><span data-stu-id="5f8ef-263">1</span></span>  <br/> |<span data-ttu-id="5f8ef-264">시간</span><span class="sxs-lookup"><span data-stu-id="5f8ef-264">Hours</span></span>  <br/> |<span data-ttu-id="5f8ef-265">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="5f8ef-265">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="5f8ef-266">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="5f8ef-266">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="5f8ef-267">CNAME</span><span class="sxs-lookup"><span data-stu-id="5f8ef-267">CNAME</span></span>  <br/> |<span data-ttu-id="5f8ef-268">1 </span><span class="sxs-lookup"><span data-stu-id="5f8ef-268">1</span></span>  <br/> |<span data-ttu-id="5f8ef-269">시간</span><span class="sxs-lookup"><span data-stu-id="5f8ef-269">Hours</span></span>  <br/> |<span data-ttu-id="5f8ef-270">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5f8ef-270">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="5f8ef-271">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="5f8ef-271">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="5f8ef-272"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="5f8ef-272"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f8ef-273">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-273">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="5f8ef-274">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-274">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="5f8ef-275">도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-275">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="5f8ef-276">대신, 두 값 집합을 모두 포함 하는  *단일*  SPF 레코드가 있도록 현재 레코드에 필수 Microsoft 값을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-276">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="5f8ef-277">시작 하려면 [이 링크](https://portal.azure.com )를 사용 하 여 Azure의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-277">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="5f8ef-278">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-278">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-구성-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="5f8ef-280">**대시보드** 페이지의 **모든 리소스** 영역에서 업데이트할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-280">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-구성-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="5f8ef-282">**DNS 영역** 영역에서 **TXT 레코드 집합**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-282">In the **DNS zone** area, select the **TXT record set**.</span></span>
    
    ![Azure-BP-구성-4-1](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. <span data-ttu-id="5f8ef-284">**레코드 집합 속성** 영역의 새 레코드 집합에 대 한 상자에서 다음 표의 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-284">In the **Record set properties** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="5f8ef-285">(드롭다운 목록에서 **Type (종류** ) 및 **TTL 단위** 값을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="5f8ef-285">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="5f8ef-286">**이름**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-286">**Name**</span></span>|<span data-ttu-id="5f8ef-287">**Type(종류)**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-287">**Type**</span></span>|<span data-ttu-id="5f8ef-288">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-288">**TTL**</span></span>|<span data-ttu-id="5f8ef-289">**TTL 단위**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-289">**TTL unit**</span></span>|<span data-ttu-id="5f8ef-290">**값**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-290">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="5f8ef-291">TXT</span><span class="sxs-lookup"><span data-stu-id="5f8ef-291">TXT</span></span>  <br/> |<span data-ttu-id="5f8ef-292">1 </span><span class="sxs-lookup"><span data-stu-id="5f8ef-292">1</span></span>  <br/> |<span data-ttu-id="5f8ef-293">시간</span><span class="sxs-lookup"><span data-stu-id="5f8ef-293">Hours</span></span>  <br/> |<span data-ttu-id="5f8ef-294">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="5f8ef-294">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="5f8ef-295">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           

    ![Azure-BP-구성-4-2](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. <span data-ttu-id="5f8ef-297">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-297">Select **Save**.</span></span>
    
    ![Azure-BP-구성-4-3](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="5f8ef-299">Microsoft 필요한 2개의 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="5f8ef-299">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="5f8ef-300"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="5f8ef-300"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="5f8ef-301">시작 하려면 [이 링크](https://portal.azure.com )를 사용 하 여 Azure의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-301">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="5f8ef-302">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-302">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-구성-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="5f8ef-304">**대시보드** 페이지의 **모든 리소스** 영역에서 업데이트할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-304">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-구성-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="5f8ef-306">도메인의 **설정** 페이지에 있는 **DNS 영역** 에서 **+ 레코드 집합**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-306">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-구성-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="5f8ef-308">처음 2개의 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-308">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="5f8ef-309">**레코드 집합 추가** 영역의 새 레코드 집합에 대 한 상자에서 다음 표의 첫 번째 행에 있는 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-309">In the **Add record set** area, in the boxes for the new record set, select the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="5f8ef-310">(드롭다운 목록에서 **Type (종류** ) 및 **TTL 단위** 값을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="5f8ef-310">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="5f8ef-311">**이름**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-311">**Name**</span></span>|<span data-ttu-id="5f8ef-312">**Type(종류)**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-312">**Type**</span></span>|<span data-ttu-id="5f8ef-313">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-313">**TTL**</span></span>|<span data-ttu-id="5f8ef-314">**TTL 단위**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-314">**TTL unit**</span></span>|<span data-ttu-id="5f8ef-315">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-315">**Priority**</span></span>|<span data-ttu-id="5f8ef-316">**Weight(가중치)**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-316">**Weight**</span></span>|<span data-ttu-id="5f8ef-317">**Port(포트)**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-317">**Port**</span></span>|<span data-ttu-id="5f8ef-318">**대상**</span><span class="sxs-lookup"><span data-stu-id="5f8ef-318">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5f8ef-319">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="5f8ef-319">_sip._tls</span></span>  <br/> |<span data-ttu-id="5f8ef-320">SRV</span><span class="sxs-lookup"><span data-stu-id="5f8ef-320">SRV</span></span>  <br/> |<span data-ttu-id="5f8ef-321">1 </span><span class="sxs-lookup"><span data-stu-id="5f8ef-321">1</span></span>  <br/> |<span data-ttu-id="5f8ef-322">시간</span><span class="sxs-lookup"><span data-stu-id="5f8ef-322">Hours</span></span>  <br/> |<span data-ttu-id="5f8ef-323">100</span><span class="sxs-lookup"><span data-stu-id="5f8ef-323">100</span></span>  <br/> |<span data-ttu-id="5f8ef-324">1 </span><span class="sxs-lookup"><span data-stu-id="5f8ef-324">1</span></span>  <br/> |<span data-ttu-id="5f8ef-325">443</span><span class="sxs-lookup"><span data-stu-id="5f8ef-325">443</span></span>  <br/> |<span data-ttu-id="5f8ef-326">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5f8ef-326">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="5f8ef-327">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="5f8ef-327">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="5f8ef-328">SRV</span><span class="sxs-lookup"><span data-stu-id="5f8ef-328">SRV</span></span>  <br/> |<span data-ttu-id="5f8ef-329">1 </span><span class="sxs-lookup"><span data-stu-id="5f8ef-329">1</span></span>  <br/> |<span data-ttu-id="5f8ef-330">시간</span><span class="sxs-lookup"><span data-stu-id="5f8ef-330">Hours</span></span>  <br/> |<span data-ttu-id="5f8ef-331">100</span><span class="sxs-lookup"><span data-stu-id="5f8ef-331">100</span></span>  <br/> |<span data-ttu-id="5f8ef-332">1 </span><span class="sxs-lookup"><span data-stu-id="5f8ef-332">1</span></span>  <br/> |<span data-ttu-id="5f8ef-333">5061</span><span class="sxs-lookup"><span data-stu-id="5f8ef-333">5061</span></span>  <br/> |<span data-ttu-id="5f8ef-334">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5f8ef-334">sipfed.online.lync.com</span></span>  <br/> 

    ![Azure-BP-구성-5-1](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. <span data-ttu-id="5f8ef-336">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-336">Select **OK**.</span></span>
    
    ![Azure-BP-구성-5-2](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. <span data-ttu-id="5f8ef-338">다른 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-338">Add the other SRV record.</span></span>
    
    <span data-ttu-id="5f8ef-339">새 레코드의 상자에서 표의 두 번째 행에 있는 값을 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-339">In the boxes for the new record, type or copy and paste the values from the second row of the table.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5f8ef-p120">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f8ef-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
