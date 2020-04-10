---
title: Azure DNS 영역에 대 한 DNS 레코드 만들기
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
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 및 Office 365의 Azure DNS 영역에 있는 다른 서비스에 대 한 DNS 레코드를 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 1c9ac04f74b205fa4a099fca634a41207e8083ba
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211053"
---
# <a name="create-dns-records-for-azure-dns-zones"></a><span data-ttu-id="78a3c-103">Azure DNS 영역에 대 한 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="78a3c-103">Create DNS records for Azure DNS zones</span></span>

 <span data-ttu-id="78a3c-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="78a3c-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="78a3c-105">Azure가 DNS 호스팅 공급자 이면이 문서에 나와 있는 단계에 따라 도메인을 확인 하 고 전자 메일, 비즈니스용 Skype Online 등에 대 한 DNS 레코드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-105">If Azure is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="78a3c-106">다음은 추가할 기본 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="78a3c-107">도메인의 NS(이름 서버) 레코드 변경</span><span class="sxs-lookup"><span data-stu-id="78a3c-107">Change your domain's nameserver (NS) records</span></span>](#change-your-domains-nameserver-ns-records)
    
- [<span data-ttu-id="78a3c-108">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="78a3c-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)

- [<span data-ttu-id="78a3c-109">사용자 도메인의 전자 메일이 Office 365로 전송되도록 MX 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="78a3c-109">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="78a3c-110">Office 365에 필요한 4 개의 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="78a3c-110">Add the four CNAME records that are required for Office 365</span></span>](#add-the-four-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="78a3c-111">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="78a3c-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="78a3c-112">Office 365에 필요한 2개의 SRV 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="78a3c-112">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="78a3c-113">Azure에서 이러한 레코드를 추가 하 고 나면 도메인이 Office 365 서비스에서 작동 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-113">After you add these records at Azure, your domain will be set up to work with Office 365 services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="78a3c-p101">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78a3c-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="78a3c-117">도메인의 NS(이름 서버) 레코드 변경</span><span class="sxs-lookup"><span data-stu-id="78a3c-117">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="78a3c-118"><a name="BKMK_NS"> </a></span><span class="sxs-lookup"><span data-stu-id="78a3c-118"><a name="BKMK_NS"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="78a3c-119">이 절차는 도메인을 구입하고 등록한 도메인 등록 기관에서 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-119">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="78a3c-120">Azure에 등록할 때 DNS 영역 내에 리소스 그룹을 만든 다음 해당 리소스 그룹에 도메인 이름을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-120">When you signed up for Azure, you created a resource group within a DNS zone, and then assigned your domain name to that resource group.</span></span> <span data-ttu-id="78a3c-121">해당 도메인 이름은 외부 도메인 등록자에 등록 됩니다. Azure는 도메인 등록 서비스를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-121">That domain name is registered to an external domain registrar; Azure does not offer domain registration services.</span></span>
  
<span data-ttu-id="78a3c-122">Office 365에서 도메인에 대 한 DNS 레코드를 확인 하 고 만들려면 먼저 도메인 등록 기관에서 이름 서버를 변경 하 여 리소스 그룹에 할당 된 Azure 이름 서버을 사용 하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-122">To verify and create DNS records for your domain in Office 365, you first need to change the nameservers at your domain registrar so that they use the Azure nameservers assigned to your resource group.</span></span>
  
<span data-ttu-id="78a3c-123">도메인 등록 기관 웹 사이트에서 도메인 이름 서버를 직접 변경하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-123">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="78a3c-124">도메인 등록 기관의 웹 사이트에서 도메인의 이름 서버를 편집할 수 있는 영역을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-124">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="78a3c-125">다음 표의 값을 사용 하 여 두 개의 이름 서버 레코드를 만들거나 기존 이름 서버 레코드를 해당 값과 일치 하도록 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-125">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span> <span data-ttu-id="78a3c-126">Azure 할당 된 이름 서버의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-126">An example of Azure assigned nameservers is shown below.</span></span>
    


<span data-ttu-id="78a3c-127">**첫 번째 이름 서버:** Azure에서 할당 된 이름 서버 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-127">**First nameserver:** Use the name server value assigned by Azure.</span></span>  
<span data-ttu-id="78a3c-128">**두 번째** 이름 서버: Azure에서 할당 된 이름 서버 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-128">**Second nameserver:** Use the name server value assigned by Azure.</span></span>  

![Redelegate-1-1](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> <span data-ttu-id="78a3c-130">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="78a3c-130">You should use at least two name server records.</span></span> <span data-ttu-id="78a3c-131">도메인 등록 기관의 웹 사이트에 다른 이름 서버가 나열 된 경우 해당 서버를 삭제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-131">If there are any other name servers listed at your domain registrar's website, you should delete them.</span></span> 
  
3. <span data-ttu-id="78a3c-132">변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-132">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="78a3c-p105">이름 서버 레코드 업데이트가 인터넷의 DNS 시스템 전체에 업데이트되기까지 몇 시간이 걸릴 수 있습니다. 그 후에는 Office 365 전자 메일 및 기타 서비스가 모두 사용자의 도메인을 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-p105">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="78a3c-135">확인을 위해 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="78a3c-135">Add a TXT record for verification</span></span>
<span data-ttu-id="78a3c-136"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="78a3c-136"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="78a3c-p106">Office 365에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Office 365에 도메인을 소유하고 있음을 증명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-p106">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="78a3c-p107">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-p107">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="78a3c-141">시작 하려면 [이 링크](https://portal.azure.com )를 사용 하 여 Azure의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-141">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="78a3c-142">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-142">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-구성-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="78a3c-144">**대시보드** 페이지의 **검색 표시줄** 을 사용 하 여 **DNS 영역**을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-144">Using the **search bar** on the **Dashboard** page, type in **DNS zones**.</span></span> <span data-ttu-id="78a3c-145">결과 표시의 **서비스** 부분 아래에서 **DNS 영역** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-145">In the results display, select **DNS zones** under the **Services** portion.</span></span> <span data-ttu-id="78a3c-146">리디렉션된 후에는 업데이트할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-146">Once you've been redirected, select the domain that you want to update.</span></span>
    
    ![Azure-BP-구성-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="78a3c-148">도메인의 **설정** 페이지에 있는 **DNS 영역** 에서 **+ 레코드 집합**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-148">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-구성-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="78a3c-150">**레코드 집합 추가** 영역의 새 레코드 집합에 대 한 상자에서 다음 표의 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-150">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="78a3c-151">(드롭다운 목록에서 **Type (종류** ) 및 **TTL 단위** 값을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="78a3c-151">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="78a3c-152">**이름**</span><span class="sxs-lookup"><span data-stu-id="78a3c-152">**Name**</span></span>|<span data-ttu-id="78a3c-153">**종류**</span><span class="sxs-lookup"><span data-stu-id="78a3c-153">**Type**</span></span>|<span data-ttu-id="78a3c-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="78a3c-154">**TTL**</span></span>|<span data-ttu-id="78a3c-155">**TTL 단위**</span><span class="sxs-lookup"><span data-stu-id="78a3c-155">**TTL unit**</span></span>|<span data-ttu-id="78a3c-156">**값**</span><span class="sxs-lookup"><span data-stu-id="78a3c-156">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="78a3c-157">TXT</span><span class="sxs-lookup"><span data-stu-id="78a3c-157">TXT</span></span>  <br/> |<span data-ttu-id="78a3c-158">1 </span><span class="sxs-lookup"><span data-stu-id="78a3c-158">1</span></span>  <br/> |<span data-ttu-id="78a3c-159">시간</span><span class="sxs-lookup"><span data-stu-id="78a3c-159">Hours</span></span>  <br/> |<span data-ttu-id="78a3c-160">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="78a3c-160">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="78a3c-161">**참고:** 이 값은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-161">**Note:** This is an example.</span></span> <span data-ttu-id="78a3c-162">여기에는 Office 365의 표에 있는 특정 **보낼 대상 또는 지점** 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-162">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="78a3c-163">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="78a3c-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Azure-BP-Verify-1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. <span data-ttu-id="78a3c-165">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-165">Select **OK**.</span></span>
  
6. <span data-ttu-id="78a3c-166">방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-166">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="78a3c-167">이제 도메인 등록 기관에 레코드가 추가되었습니다. Office 365로 돌아가서 Office 365에 레코드를 찾을 것을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-167">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="78a3c-168">Office 365에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-168">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="78a3c-169">I관리 센터에서 \*\* 설정 \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="78a3c-169">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="78a3c-170">**도메인** 페이지에서 확인 중인 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-170">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="78a3c-171">**설정** 페이지에서 **설정 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-171">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="78a3c-172">**도메인 확인** 페이지에서 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-172">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="78a3c-p111">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78a3c-p111">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="78a3c-176">사용자 도메인의 전자 메일이 Office 365로 전송되도록 MX 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="78a3c-176">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="78a3c-177"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="78a3c-177"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="78a3c-178">시작 하려면 [이 링크](https://portal.azure.com )를 사용 하 여 Azure의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-178">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="78a3c-179">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-179">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-구성-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="78a3c-181">**대시보드** 페이지의 **모든 리소스** 영역에서 업데이트할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-181">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-구성-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="78a3c-183">도메인의 **설정** 페이지에 있는 **DNS 영역** 에서 **+ 레코드 집합**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-183">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-구성-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="78a3c-185">**레코드 집합 추가** 영역의 새 레코드 집합에 대 한 상자에서 다음 표의 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-185">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="78a3c-186">(드롭다운 목록에서 **Type (종류** ) 및 **TTL 단위** 값을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="78a3c-186">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="78a3c-187">**이름**</span><span class="sxs-lookup"><span data-stu-id="78a3c-187">**Name**</span></span>|<span data-ttu-id="78a3c-188">**종류**</span><span class="sxs-lookup"><span data-stu-id="78a3c-188">**Type**</span></span>|<span data-ttu-id="78a3c-189">**TTL**</span><span class="sxs-lookup"><span data-stu-id="78a3c-189">**TTL**</span></span>|<span data-ttu-id="78a3c-190">**TTL 단위**</span><span class="sxs-lookup"><span data-stu-id="78a3c-190">**TTL unit**</span></span>|<span data-ttu-id="78a3c-191">**기본 설정**</span><span class="sxs-lookup"><span data-stu-id="78a3c-191">**Preference**</span></span>|<span data-ttu-id="78a3c-192">**메일 교환**</span><span class="sxs-lookup"><span data-stu-id="78a3c-192">**Mail Exchange**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="78a3c-193">MX</span><span class="sxs-lookup"><span data-stu-id="78a3c-193">MX</span></span>  <br/> |<span data-ttu-id="78a3c-194">1 </span><span class="sxs-lookup"><span data-stu-id="78a3c-194">1</span></span>  <br/> |<span data-ttu-id="78a3c-195">시간</span><span class="sxs-lookup"><span data-stu-id="78a3c-195">Hours</span></span>  <br/> |<span data-ttu-id="78a3c-196">10 </span><span class="sxs-lookup"><span data-stu-id="78a3c-196">10</span></span>  <br/> <span data-ttu-id="78a3c-197">우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78a3c-197">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="78a3c-198">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="78a3c-198">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="78a3c-199">**참고:** Office 365 계정에서 \* \<도메인\> 키\* 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-199">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="78a3c-200">이 값을 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="78a3c-200">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Azure-BP-구성-2-1](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. <span data-ttu-id="78a3c-202">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-202">Select **OK**.</span></span>
    
    ![Azure-BP-구성-2-2](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. <span data-ttu-id="78a3c-204">**Mx 레코드** 구역에 다른 mx 레코드가 나열 되어 있으면 해당 레코드를 삭제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-204">If there are any other MX records listed in the **MX Records** section, you must delete them.</span></span> 
    
    <span data-ttu-id="78a3c-205">먼저 **DNS 영역** 에서 **MX 레코드 집합**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-205">First, in the **DNS zone** area, select the **MX Record set**.</span></span>
    
    ![Azure-BP-구성-2-3](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    <span data-ttu-id="78a3c-207">그런 다음 삭제 하려는 MX 레코드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-207">Next, select the MX record you want to delete.</span></span>
    
    ![Azure-BP-구성-2-4](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. <span data-ttu-id="78a3c-209">상황에 **맞는 메뉴 (...)** 를 선택한 다음 **제거**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-209">Select the **Context menu (…)**, and then choose **Remove**.</span></span>
    
    ![Azure-BP-구성-2-5](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. <span data-ttu-id="78a3c-211">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-211">Select **Save**.</span></span>
    
    ![Azure-BP-구성-2-6](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="78a3c-213">Office 365에 필요한 4 개의 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="78a3c-213">Add the four CNAME records that are required for Office 365</span></span>
<span data-ttu-id="78a3c-214"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="78a3c-214"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="78a3c-215">시작 하려면 [이 링크](https://portal.azure.com )를 사용 하 여 Azure의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-215">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="78a3c-216">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-216">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-구성-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="78a3c-218">**대시보드** 페이지의 **모든 리소스** 영역에서 업데이트할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-218">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-구성-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="78a3c-220">도메인의 **설정** 페이지에 있는 **DNS 영역** 에서 **+ 레코드 집합**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-220">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-구성-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="78a3c-222">4 개의 CNAME 레코드 중 처음 일부를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-222">Add the first of the four CNAME records.</span></span>
    
    <span data-ttu-id="78a3c-223">**레코드 집합 추가** 영역의 새 레코드 집합 용 상자에 다음 표에 있는 첫 번째 행의 값을 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-223">In the **Add record set** area, in the boxes for the new record set, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="78a3c-224">(드롭다운 목록에서 **Type (종류** ) 및 **TTL 단위** 값을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="78a3c-224">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="78a3c-225">**이름**</span><span class="sxs-lookup"><span data-stu-id="78a3c-225">**Name**</span></span>|<span data-ttu-id="78a3c-226">**종류**</span><span class="sxs-lookup"><span data-stu-id="78a3c-226">**Type**</span></span>|<span data-ttu-id="78a3c-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="78a3c-227">**TTL**</span></span>|<span data-ttu-id="78a3c-228">**TTL 단위**</span><span class="sxs-lookup"><span data-stu-id="78a3c-228">**TTL unit**</span></span>|<span data-ttu-id="78a3c-229">**별칭**</span><span class="sxs-lookup"><span data-stu-id="78a3c-229">**Alias**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="78a3c-230">autodiscover</span><span class="sxs-lookup"><span data-stu-id="78a3c-230">autodiscover</span></span>  <br/> |<span data-ttu-id="78a3c-231">CNAME</span><span class="sxs-lookup"><span data-stu-id="78a3c-231">CNAME</span></span>  <br/> |<span data-ttu-id="78a3c-232">1 </span><span class="sxs-lookup"><span data-stu-id="78a3c-232">1</span></span>  <br/> |<span data-ttu-id="78a3c-233">시간</span><span class="sxs-lookup"><span data-stu-id="78a3c-233">Hours</span></span>  <br/> |<span data-ttu-id="78a3c-234">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="78a3c-234">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="78a3c-235">sip</span><span class="sxs-lookup"><span data-stu-id="78a3c-235">sip</span></span>  <br/> |<span data-ttu-id="78a3c-236">CNAME</span><span class="sxs-lookup"><span data-stu-id="78a3c-236">CNAME</span></span>  <br/> |<span data-ttu-id="78a3c-237">1 </span><span class="sxs-lookup"><span data-stu-id="78a3c-237">1</span></span>  <br/> |<span data-ttu-id="78a3c-238">시간</span><span class="sxs-lookup"><span data-stu-id="78a3c-238">Hours</span></span>  <br/> |<span data-ttu-id="78a3c-239">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="78a3c-239">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="78a3c-240">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="78a3c-240">lyncdiscover</span></span>  <br/> |<span data-ttu-id="78a3c-241">CNAME</span><span class="sxs-lookup"><span data-stu-id="78a3c-241">CNAME</span></span>  <br/> |<span data-ttu-id="78a3c-242">1 </span><span class="sxs-lookup"><span data-stu-id="78a3c-242">1</span></span>  <br/> |<span data-ttu-id="78a3c-243">시간</span><span class="sxs-lookup"><span data-stu-id="78a3c-243">Hours</span></span>  <br/> |<span data-ttu-id="78a3c-244">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="78a3c-244">webdir.online.lync.com</span></span>  <br/> |
    
   
    ![Azure-BP-구성-3-1](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. <span data-ttu-id="78a3c-246">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-246">Select **OK**.</span></span>
    
    ![Azure-BP-구성-3-2](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. <span data-ttu-id="78a3c-248">나머지 3 개의 CNAME 레코드를 각각 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-248">Add each of the other three CNAME records.</span></span>
    
    <span data-ttu-id="78a3c-249">**DNS 영역** 영역에서 **+ 레코드 집합**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-249">In the **DNS zone** area, select **+ Record set**.</span></span> <span data-ttu-id="78a3c-250">그런 다음 빈 레코드 집합에서 표의 다음 행 값을 사용 하 여 레코드를 만들고 **확인** 을 선택 하 여 해당 레코드를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-250">Then, in the empty record set, create a record by using the values from the next row in the table, and again select **OK** to complete that record.</span></span> 
    
    <span data-ttu-id="78a3c-251">4 개의 CNAME 레코드를 모두 만들 때까지이 프로세스를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-251">Repeat this process until you have created all four CNAME records.</span></span>
    
7.  <span data-ttu-id="78a3c-252">반드시 MDM에 대 한 2 개의 CNAME 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-252">(Optional) Add 2 CNAME records for MDM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78a3c-253">Office 365용 MDM (Mobile Device Management)이있는 경우 두 개의 추가 CNAME 레코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-253">If you have Mobile Device Management (MDM) for Office 365, then you must create two additional CNAME records.</span></span> <span data-ttu-id="78a3c-254">다른 4개의 CNAME 레코드를 만드는 데 사용한 절차를 따르되 다음 표의 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="78a3c-255">(MDM이 없는 경우에는이 단계를 건너뛰어도 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="78a3c-255">(If you do not have MDM, you can skip this step.)</span></span> 
  
|<span data-ttu-id="78a3c-256">**이름**</span><span class="sxs-lookup"><span data-stu-id="78a3c-256">**Name**</span></span>|<span data-ttu-id="78a3c-257">**종류**</span><span class="sxs-lookup"><span data-stu-id="78a3c-257">**Type**</span></span>|<span data-ttu-id="78a3c-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="78a3c-258">**TTL**</span></span>|<span data-ttu-id="78a3c-259">**TTL 단위**</span><span class="sxs-lookup"><span data-stu-id="78a3c-259">**TTL unit**</span></span>|<span data-ttu-id="78a3c-260">**별칭**</span><span class="sxs-lookup"><span data-stu-id="78a3c-260">**Alias**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="78a3c-261">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="78a3c-261">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="78a3c-262">CNAME</span><span class="sxs-lookup"><span data-stu-id="78a3c-262">CNAME</span></span>  <br/> |<span data-ttu-id="78a3c-263">1 </span><span class="sxs-lookup"><span data-stu-id="78a3c-263">1</span></span>  <br/> |<span data-ttu-id="78a3c-264">시간</span><span class="sxs-lookup"><span data-stu-id="78a3c-264">Hours</span></span>  <br/> |<span data-ttu-id="78a3c-265">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="78a3c-265">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="78a3c-266">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="78a3c-266">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="78a3c-267">CNAME</span><span class="sxs-lookup"><span data-stu-id="78a3c-267">CNAME</span></span>  <br/> |<span data-ttu-id="78a3c-268">1 </span><span class="sxs-lookup"><span data-stu-id="78a3c-268">1</span></span>  <br/> |<span data-ttu-id="78a3c-269">시간</span><span class="sxs-lookup"><span data-stu-id="78a3c-269">Hours</span></span>  <br/> |<span data-ttu-id="78a3c-270">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="78a3c-270">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="78a3c-271">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="78a3c-271">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="78a3c-272"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="78a3c-272"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="78a3c-273">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-273">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="78a3c-274">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-274">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="78a3c-275">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="78a3c-275">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="78a3c-276">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="78a3c-276">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="78a3c-277">시작 하려면 [이 링크](https://portal.azure.com )를 사용 하 여 Azure의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-277">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="78a3c-278">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-278">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-구성-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="78a3c-280">**대시보드** 페이지의 **모든 리소스** 영역에서 업데이트할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-280">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-구성-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="78a3c-282">**DNS 영역** 영역에서 **TXT 레코드 집합**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-282">In the **DNS zone** area, select the **TXT record set**.</span></span>
    
    ![Azure-BP-구성-4-1](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. <span data-ttu-id="78a3c-284">**레코드 집합 속성** 영역의 새 레코드 집합에 대 한 상자에서 다음 표의 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-284">In the **Record set properties** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="78a3c-285">(드롭다운 목록에서 **Type (종류** ) 및 **TTL 단위** 값을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="78a3c-285">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="78a3c-286">**이름**</span><span class="sxs-lookup"><span data-stu-id="78a3c-286">**Name**</span></span>|<span data-ttu-id="78a3c-287">**종류**</span><span class="sxs-lookup"><span data-stu-id="78a3c-287">**Type**</span></span>|<span data-ttu-id="78a3c-288">**TTL**</span><span class="sxs-lookup"><span data-stu-id="78a3c-288">**TTL**</span></span>|<span data-ttu-id="78a3c-289">**TTL 단위**</span><span class="sxs-lookup"><span data-stu-id="78a3c-289">**TTL unit**</span></span>|<span data-ttu-id="78a3c-290">**값**</span><span class="sxs-lookup"><span data-stu-id="78a3c-290">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="78a3c-291">TXT</span><span class="sxs-lookup"><span data-stu-id="78a3c-291">TXT</span></span>  <br/> |<span data-ttu-id="78a3c-292">1 </span><span class="sxs-lookup"><span data-stu-id="78a3c-292">1</span></span>  <br/> |<span data-ttu-id="78a3c-293">시간</span><span class="sxs-lookup"><span data-stu-id="78a3c-293">Hours</span></span>  <br/> |<span data-ttu-id="78a3c-294">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="78a3c-294">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="78a3c-295">**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           

    ![Azure-BP-구성-4-2](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. <span data-ttu-id="78a3c-297">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-297">Select **Save**.</span></span>
    
    ![Azure-BP-구성-4-3](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="78a3c-299">Office 365에 필요한 2개의 SRV 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="78a3c-299">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="78a3c-300"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="78a3c-300"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="78a3c-301">시작 하려면 [이 링크](https://portal.azure.com )를 사용 하 여 Azure의 도메인 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-301">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="78a3c-302">먼저 로그인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-302">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-구성-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="78a3c-304">**대시보드** 페이지의 **모든 리소스** 영역에서 업데이트할 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-304">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-구성-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="78a3c-306">도메인의 **설정** 페이지에 있는 **DNS 영역** 에서 **+ 레코드 집합**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-306">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-구성-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="78a3c-308">처음 2개의 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-308">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="78a3c-309">**레코드 집합 추가** 영역의 새 레코드 집합에 대 한 상자에서 다음 표의 첫 번째 행에 있는 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-309">In the **Add record set** area, in the boxes for the new record set, select the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="78a3c-310">(드롭다운 목록에서 **Type (종류** ) 및 **TTL 단위** 값을 선택 합니다.)</span><span class="sxs-lookup"><span data-stu-id="78a3c-310">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="78a3c-311">**이름**</span><span class="sxs-lookup"><span data-stu-id="78a3c-311">**Name**</span></span>|<span data-ttu-id="78a3c-312">**종류**</span><span class="sxs-lookup"><span data-stu-id="78a3c-312">**Type**</span></span>|<span data-ttu-id="78a3c-313">**TTL**</span><span class="sxs-lookup"><span data-stu-id="78a3c-313">**TTL**</span></span>|<span data-ttu-id="78a3c-314">**TTL 단위**</span><span class="sxs-lookup"><span data-stu-id="78a3c-314">**TTL unit**</span></span>|<span data-ttu-id="78a3c-315">**Priority(우선 순위)**</span><span class="sxs-lookup"><span data-stu-id="78a3c-315">**Priority**</span></span>|<span data-ttu-id="78a3c-316">**Weight(가중치)**</span><span class="sxs-lookup"><span data-stu-id="78a3c-316">**Weight**</span></span>|<span data-ttu-id="78a3c-317">**Port(포트)**</span><span class="sxs-lookup"><span data-stu-id="78a3c-317">**Port**</span></span>|<span data-ttu-id="78a3c-318">**대상**</span><span class="sxs-lookup"><span data-stu-id="78a3c-318">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="78a3c-319">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="78a3c-319">_sip._tls</span></span>  <br/> |<span data-ttu-id="78a3c-320">SRV</span><span class="sxs-lookup"><span data-stu-id="78a3c-320">SRV</span></span>  <br/> |<span data-ttu-id="78a3c-321">1 </span><span class="sxs-lookup"><span data-stu-id="78a3c-321">1</span></span>  <br/> |<span data-ttu-id="78a3c-322">시간</span><span class="sxs-lookup"><span data-stu-id="78a3c-322">Hours</span></span>  <br/> |<span data-ttu-id="78a3c-323">100</span><span class="sxs-lookup"><span data-stu-id="78a3c-323">100</span></span>  <br/> |<span data-ttu-id="78a3c-324">1 </span><span class="sxs-lookup"><span data-stu-id="78a3c-324">1</span></span>  <br/> |<span data-ttu-id="78a3c-325">443</span><span class="sxs-lookup"><span data-stu-id="78a3c-325">443</span></span>  <br/> |<span data-ttu-id="78a3c-326">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="78a3c-326">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="78a3c-327">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="78a3c-327">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="78a3c-328">SRV</span><span class="sxs-lookup"><span data-stu-id="78a3c-328">SRV</span></span>  <br/> |<span data-ttu-id="78a3c-329">1 </span><span class="sxs-lookup"><span data-stu-id="78a3c-329">1</span></span>  <br/> |<span data-ttu-id="78a3c-330">시간</span><span class="sxs-lookup"><span data-stu-id="78a3c-330">Hours</span></span>  <br/> |<span data-ttu-id="78a3c-331">100</span><span class="sxs-lookup"><span data-stu-id="78a3c-331">100</span></span>  <br/> |<span data-ttu-id="78a3c-332">1 </span><span class="sxs-lookup"><span data-stu-id="78a3c-332">1</span></span>  <br/> |<span data-ttu-id="78a3c-333">5061</span><span class="sxs-lookup"><span data-stu-id="78a3c-333">5061</span></span>  <br/> |<span data-ttu-id="78a3c-334">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="78a3c-334">sipfed.online.lync.com</span></span>  <br/> 

    ![Azure-BP-구성-5-1](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. <span data-ttu-id="78a3c-336">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-336">Select **OK**.</span></span>
    
    ![Azure-BP-구성-5-2](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. <span data-ttu-id="78a3c-338">다른 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-338">Add the other SRV record.</span></span>
    
    <span data-ttu-id="78a3c-339">새 레코드의 상자에서 표의 두 번째 행에 있는 값을 입력 하거나 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="78a3c-339">In the boxes for the new record, type or copy and paste the values from the second row of the table.</span></span>
    
> [!NOTE]
> <span data-ttu-id="78a3c-p120">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78a3c-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
