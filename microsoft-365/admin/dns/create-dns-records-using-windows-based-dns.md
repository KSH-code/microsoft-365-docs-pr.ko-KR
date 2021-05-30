---
title: WINDOWS DNS를 사용하여 Microsoft용 DNS 레코드 만들기
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
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: Microsoft용 도메인 기반 DNS에서 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 Windows DNS 레코드를 설정하는 방법을 배워야 합니다.
ms.openlocfilehash: b9088fe3efd58700db0234a2839665a783731eb0
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706118"
---
# <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a><span data-ttu-id="cee0c-103">WINDOWS DNS를 사용하여 Microsoft용 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="cee0c-103">Create DNS records for Microsoft using Windows-based DNS</span></span>

 <span data-ttu-id="cee0c-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="cee0c-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
   
<span data-ttu-id="cee0c-105">Windows 기반 DNS를 사용하여 자체 DNS 레코드를 호스트하는 경우 이 문서의 단계에 따라 전자 메일, 비즈니스용 Skype Online 등에 대한 레코드를 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="cee0c-105">If you host your own DNS records using Windows-based DNS, follow the steps in this article to set up your records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="cee0c-106">시작하려면 업데이트할 수 있도록 Windows [DNS에서 DNS](#find-your-dns-records-in-windows-based-dns) 레코드를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-106">To get started, you need to [find your DNS records in Windows-based DNS](#find-your-dns-records-in-windows-based-dns) so you can update them.</span></span> <span data-ttu-id="cee0c-107">또한 Microsoft와의 동기화를 계획하는 경우 라우팅할 수 없는 전자 메일 주소가 [On-prem Active Directory](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory)에서 UPN으로 사용되는 것을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cee0c-107">Also, if you're planning to synchronize your on-premises Active Directory with Microsoft, see [Non-routable email address used as a UPN in your on-prem Active Directory](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory).</span></span>
  
<span data-ttu-id="cee0c-108">DNS 레코드를 추가한 후 메일 흐름 또는 기타 문제를 해결하는 데 문제가 발생하면 도메인 이름 또는 DNS 레코드를 변경한 후 문제 [해결을 참조합니다.](../get-help-with-domains/find-and-fix-issues.md)</span><span class="sxs-lookup"><span data-stu-id="cee0c-108">Trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a><span data-ttu-id="cee0c-109">Windows 기반 DNS에서 DNS 레코드 찾기</span><span class="sxs-lookup"><span data-stu-id="cee0c-109">Find your DNS records in Windows-based DNS</span></span>
<span data-ttu-id="cee0c-110"><a name="BKMK_find_your_dns_1"></a> 도메인에 대한 DNS 레코드가 있는 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-110"><a name="BKMK_find_your_dns_1"> </a> Go to the page that has the DNS records for your domain.</span></span> <span data-ttu-id="cee0c-111">Windows Server 2008에서 작업하는 경우 실행 시작으로   >  **이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="cee0c-111">If you're working in Windows Server 2008, go to **Start** > **Run**.</span></span> <span data-ttu-id="cee0c-112">If you're working in Windows Server 2012, press the Windows key and **r**.</span><span class="sxs-lookup"><span data-stu-id="cee0c-112">If you're working in Windows Server 2012, press the Windows key and **r**.</span></span> <span data-ttu-id="cee0c-113">**dnsmgmnt.msc 를 입력하고** 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cee0c-113">Type **dnsmgmnt.msc**, and then select **OK**.</span></span> <span data-ttu-id="cee0c-114">DNS 관리자에서 정방 **\<DNS server name\> \> 응답 영역 을 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="cee0c-114">In DNS Manager, expand **\<DNS server name\>  \> Forward Lookup Zones**.</span></span> <span data-ttu-id="cee0c-115">도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-115">Select your domain.</span></span> <span data-ttu-id="cee0c-116">이제 DNS 레코드를 만들 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-116">You're now ready to create the DNS records.</span></span>
   
## <a name="add-mx-record"></a><span data-ttu-id="cee0c-117">MX 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="cee0c-117">Add MX record</span></span>
<span data-ttu-id="cee0c-118"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="cee0c-118"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="cee0c-119">도메인의 전자 메일이 Microsoft로 전송될 수 있도록 MX 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-119">Add an MX record so email for your domain will come to Microsoft.</span></span>
- <span data-ttu-id="cee0c-120">추가할 MX 레코드에는 .mail.protection.outlook.com 값(여기서  \<MX token\> \<MX token\> 은 MSxxxx와 같은 값)을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-120">The MX record you'll add includes a value (the **Points to address** value) that looks something like this: \<MX token\>.mail.protection.outlook.com, where \<MX token\> is a value like MSxxxxxxx.</span></span> 
- <span data-ttu-id="cee0c-121">Microsoft의 DNS 레코드 추가 페이지의 Exchange Online 섹션에 있는 MX 행에서 주소 지점에 나열된 값을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-121">From the MX row in the Exchange Online section of the Add DNS records page in Microsoft, copy the value listed under Points to address.</span></span> <span data-ttu-id="cee0c-122">이 작업에서 만드는 레코드에 이 값을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-122">You'll use this value in the record you're creating in this task.</span></span> 
- <span data-ttu-id="cee0c-123">도메인의 DNS 관리자 페이지에서 작업   >  **메일 교환기(MX) 로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="cee0c-123">On the DNS Manager page for the domain, go to **Action** > **Mail Exchanger (MX)**.</span></span> <span data-ttu-id="cee0c-124">도메인에 대한 이 페이지를 찾으십시오. Windows [기반 DNS에서 DNS 레코드 찾기를 참조하세요.](#find-your-dns-records-in-windows-based-dns)</span><span class="sxs-lookup"><span data-stu-id="cee0c-124">To find this page for the domain, see [Find your DNS records in Windows-based DNS](#find-your-dns-records-in-windows-based-dns).</span></span>  
- <span data-ttu-id="cee0c-125">새 **자원 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정되어 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="cee0c-125">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span> 
    - <span data-ttu-id="cee0c-126">호스트 이름: </span><span class="sxs-lookup"><span data-stu-id="cee0c-126">Host Name:</span></span> 
    - <span data-ttu-id="cee0c-127">@Address: 방금 Microsoft에서 복사한 지점 주소 값을 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-127">@Address: Paste the Points to address  value that you just copied from Microsoft here.</span></span>  
    - <span data-ttu-id="cee0c-128">Pref:</span><span class="sxs-lookup"><span data-stu-id="cee0c-128">Pref:</span></span> 
- <span data-ttu-id="cee0c-129">변경 **내용 저장을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cee0c-129">Select **Save Changes**.</span></span>
- <span data-ttu-id="cee0c-130">사용되지 않는 MX 레코드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-130">Remove any obsolete MX records.</span></span> <span data-ttu-id="cee0c-131">전자 메일을 다른 곳에서 라우팅하는 이 도메인의 이전 MX 레코드가 있는 경우 각 이전 레코드 옆의 확인란을 선택한 다음 삭제 확인 **을**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cee0c-131">If you have any old MX records for this domain that route email somewhere else, select the check box next to each old record, and then select **Delete** > **OK**.</span></span> 
   
## <a name="add-cname-records"></a><span data-ttu-id="cee0c-132">CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="cee0c-132">Add CNAME records</span></span>
<span data-ttu-id="cee0c-133"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="cee0c-133"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="cee0c-134">Microsoft에 필요한 CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-134">Add the CNAME records that are required for Microsoft.</span></span> <span data-ttu-id="cee0c-135">Microsoft에 추가 CNAME 레코드가 나열되어 있는 경우 여기에 표시된 동일한 일반 단계에 따라 해당 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-135">If additional CNAME records are listed in Microsoft, add those following the same general steps shown here.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="cee0c-136">Microsoft용 MDM(모바일 장치 관리)이 있는 경우 두 개의 CNAME 레코드를 추가로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-136">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="cee0c-137">다른 4개의 CNAME 레코드를 만드는 데 사용한 절차를 따르되 다음 표의 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-137">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="cee0c-138">(MDM이 없는 경우 이 단계를 건너뛸 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="cee0c-138">(If you do not have MDM, you can skip this step.)</span></span> 

- <span data-ttu-id="cee0c-139">도메인의 DNS 관리자 페이지에서 작업   >  **CNAME(CNAME)으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="cee0c-139">On the DNS Manager page for the domain, go to **Action** > **CNAME (CNAME)**.</span></span>
- <span data-ttu-id="cee0c-140">새 **자원 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정되어 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="cee0c-140">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="cee0c-141">호스트 이름: autodiscover</span><span class="sxs-lookup"><span data-stu-id="cee0c-141">Host Name: autodiscover</span></span>
    - <span data-ttu-id="cee0c-142">유형:</span><span class="sxs-lookup"><span data-stu-id="cee0c-142">Type:</span></span> 
    - <span data-ttu-id="cee0c-143">CNAMEAddress: autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="cee0c-143">CNAMEAddress: autodiscover.outlook.com</span></span>
- <span data-ttu-id="cee0c-144">**O K를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-144">Select **O** K.</span></span>

<span data-ttu-id="cee0c-145">SIP CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-145">Add the SIP CNAME record.</span></span> 
- <span data-ttu-id="cee0c-146">도메인의 DNS 관리자 페이지에서 작업  \> **CNAME(CNAME)으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="cee0c-146">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
- <span data-ttu-id="cee0c-147">새 **자원 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정되어 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="cee0c-147">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="cee0c-148">호스트 이름: sip</span><span class="sxs-lookup"><span data-stu-id="cee0c-148">Host Name: sip</span></span>
    - <span data-ttu-id="cee0c-149">형식: CNAME</span><span class="sxs-lookup"><span data-stu-id="cee0c-149">Type: CNAME</span></span>
    - <span data-ttu-id="cee0c-150">주소: sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cee0c-150">Address: sipdir.online.lync.com</span></span>
- <span data-ttu-id="cee0c-151">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-151">Select **OK**.</span></span>

<span data-ttu-id="cee0c-152">비즈니스용 Skype Online 자동 검색 CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-152">Add the Skype for Business Online Autodiscover CNAME record.</span></span>  
- <span data-ttu-id="cee0c-153">도메인의 DNS 관리자 페이지에서 작업  \> **CNAME(CNAME)으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="cee0c-153">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> <span data-ttu-id="cee0c-154">새 **자원 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정되어 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="cee0c-154">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="cee0c-155">호스트 이름: lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="cee0c-155">Host Name: lyncdiscover</span></span>
    - <span data-ttu-id="cee0c-156">형식: CNAME</span><span class="sxs-lookup"><span data-stu-id="cee0c-156">Type: CNAME</span></span>
    - <span data-ttu-id="cee0c-157">주소: webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cee0c-157">Address: webdir.online.lync.com</span></span>
- <span data-ttu-id="cee0c-158">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-158">Select **OK**.</span></span>
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft"></a><span data-ttu-id="cee0c-159">Microsoft용 MDM(모바일 장치 관리)에 대한 두 개의 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="cee0c-159">Add two CNAME records for Mobile Device Management (MDM) for Microsoft</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cee0c-160">Microsoft용 MDM(모바일 장치 관리)이 있는 경우 두 개의 CNAME 레코드를 추가로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-160">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="cee0c-161">다른 4개의 CNAME 레코드를 만드는 데 사용한 절차를 따르되 다음 표의 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-161">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="cee0c-162">>(MDM이 없는 경우 이 단계를 건너뛸 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="cee0c-162">>(If you do not have MDM, you can skip this step.)</span></span> 
  

<span data-ttu-id="cee0c-163">MDM Enterpriseregistration CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-163">Add the MDM Enterpriseregistration CNAME record.</span></span>  
- <span data-ttu-id="cee0c-164">도메인의 DNS 관리자 페이지에서 작업  \> **CNAME(CNAME)으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="cee0c-164">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
- <span data-ttu-id="cee0c-165">새 **자원 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정되어 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="cee0c-165">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
- <span data-ttu-id="cee0c-166">호스트 이름: enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="cee0c-166">Host Name: enterpriseregistration</span></span>
- <span data-ttu-id="cee0c-167">형식: CNAME</span><span class="sxs-lookup"><span data-stu-id="cee0c-167">Type: CNAME</span></span>
- <span data-ttu-id="cee0c-168">주소: enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="cee0c-168">Address: enterpriseregistration.windows.net</span></span>
- <span data-ttu-id="cee0c-169">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-169">Select **OK**.</span></span> 

<span data-ttu-id="cee0c-170">MDM Enterpriseenrollment CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-170">Add the MDM Enterpriseenrollment CNAME record.</span></span> 
-  <span data-ttu-id="cee0c-171">도메인의 DNS 관리자 페이지에서 작업  \> **CNAME(CNAME)으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="cee0c-171">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
-  <span data-ttu-id="cee0c-172">새 **자원 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정되어 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="cee0c-172">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="cee0c-173">호스트 이름: enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="cee0c-173">Host Name: enterpriseenrollment</span></span>
    - <span data-ttu-id="cee0c-174">형식: CNAME</span><span class="sxs-lookup"><span data-stu-id="cee0c-174">Type: CNAME</span></span>
    - <span data-ttu-id="cee0c-175">주소: enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cee0c-175">Address: enterpriseenrollment-s.manage.microsoft.com</span></span>
- <span data-ttu-id="cee0c-176">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-176">Select **OK**.</span></span>
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="cee0c-177">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="cee0c-177">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="cee0c-178"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="cee0c-178"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="cee0c-179">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-179">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="cee0c-180">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-180">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="cee0c-181">도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="cee0c-181">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="cee0c-182">대신 두 값 집합을 모두 포함하는  *단일*  SPF 레코드가 있도록 현재 레코드에 필요한 Microsoft 값을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-182">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="cee0c-183">스팸 메일을 방지하는 데 도움이 되도록 도메인의 SPF TXT 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-183">Add the SPF TXT record for your domain to help prevent email spam.</span></span>
  
- <span data-ttu-id="cee0c-p111">이 레코드의 TXT 값에 마케팅 전자 메일의 문자열과 같은 다른 문자열이 이미 있을 수 있습니다. 이 경우 해당 문자열은 그대로 두고 이 문자열을 큰따옴표로 구분하여 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-p111">You might already have other strings in the TXT value for this record (such as strings for marketing email), which is fine. Leave those strings in place and add this one, placing double-quotes around each string to separate them.</span></span> 
- <span data-ttu-id="cee0c-186">도메인의 DNS 관리자 페이지에서 작업  \> **텍스트(TXT)로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="cee0c-186">On the DNS Manager page for your domain, go to **Action** \> **Text (TXT)**.</span></span> 
-  <span data-ttu-id="cee0c-187">새 **자원 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정되어 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="cee0c-187">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values.</span></span> 
 > [!IMPORTANT]
> <span data-ttu-id="cee0c-188">일부 Windows DNS 관리자에서는 txt 레코드를 만들 때 홈 이름이 기본적으로 상위 도메인으로 설정될 수 있도록 도메인이 설정되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-188">In some versions of Windows DNS Manager, the domain may have been set up so that when you create a txt record, the home name defaults to the parent domain.</span></span> <span data-ttu-id="cee0c-189">이 경우 TXT 레코드를 추가할 때 호스트 이름을 @ 또는 도메인 이름으로 설정하는 대신 비어 있음(값 없음)으로 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="cee0c-189">In this situation, when adding a TXT record, set the host name to blank (no value) instead of setting it to @ or the domain name.</span></span> 

-  <span data-ttu-id="cee0c-190">호스트 유형: @</span><span class="sxs-lookup"><span data-stu-id="cee0c-190">Host type: @</span></span>
-  <span data-ttu-id="cee0c-191">레코드 종류: TXT</span><span class="sxs-lookup"><span data-stu-id="cee0c-191">Record Type: TXT</span></span>
-  <span data-ttu-id="cee0c-192">주소: v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="cee0c-192">Address: v=spf1 include:spf.protection.outlook.com -all</span></span> 
         
-  <span data-ttu-id="cee0c-193">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-193">Select **OK**.</span></span>
   
## <a name="add-srv-records"></a><span data-ttu-id="cee0c-194">SRV 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="cee0c-194">Add SRV records</span></span>
<span data-ttu-id="cee0c-195"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="cee0c-195"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="cee0c-196">Microsoft에 필요한 두 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-196">Add the two SRV records that are required for Microsoft.</span></span>

<span data-ttu-id="cee0c-197">비즈니스용 Skype Online 웹 회의에 대한 SIP SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-197">Add the SIP SRV record for Skype for Business Online web conferencing.</span></span>  <br/> 
-  <span data-ttu-id="cee0c-198">도메인의 DNS 관리자 페이지에서 작업 **기타** 새 \> **레코드로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="cee0c-198">On the DNS Manager page for your domain, go to **Action** \> **Other New Records**.</span></span> 
-   <span data-ttu-id="cee0c-199">리소스 **레코드 종류 창에서** **SRV(서비스 위치)** 를 선택한 다음 레코드 만들기 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cee0c-199">In the **Resource Record Type** window, select **Service Location (SRV)**, and then select **Create Record**.</span></span> 
-   <span data-ttu-id="cee0c-200">새 **자원 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정되어 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="cee0c-200">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    -  <span data-ttu-id="cee0c-201">서비스: _sip</span><span class="sxs-lookup"><span data-stu-id="cee0c-201">Service: _sip</span></span>
    -  <span data-ttu-id="cee0c-202">프로토콜: _tls</span><span class="sxs-lookup"><span data-stu-id="cee0c-202">Protocol: _tls</span></span>
    -  <span data-ttu-id="cee0c-203">우선 순위: 100</span><span class="sxs-lookup"><span data-stu-id="cee0c-203">Priority: 100</span></span>
    -  <span data-ttu-id="cee0c-204">가중치: 1</span><span class="sxs-lookup"><span data-stu-id="cee0c-204">Weight: 1</span></span>
    -  <span data-ttu-id="cee0c-205">포트: 443</span><span class="sxs-lookup"><span data-stu-id="cee0c-205">Port: 443</span></span>
    -  <span data-ttu-id="cee0c-206">대상(호스트 이름): sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cee0c-206">Target (Hostname): sipdir.online.lync.com</span></span>
-  <span data-ttu-id="cee0c-207">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-207">Select **OK**.</span></span> 


<span data-ttu-id="cee0c-208">비즈니스용 Skype Online 페더레이션에 대한 SIP SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-208">Add the SIP SRV record for Skype for Business Online federation.</span></span>  
-  <span data-ttu-id="cee0c-209">도메인의 DNS 관리자 페이지에서 작업 **기타** 새 \> **레코드로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="cee0c-209">On the DNS Manager page for your domain, go to **Action** \> **Other New Records**.</span></span>  
-  <span data-ttu-id="cee0c-210">리소스 **레코드 종류 창에서** **SRV(서비스 위치)** 를 선택한 다음 레코드 만들기 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cee0c-210">In the **Resource Record Type** window, select **Service Location (SRV)**, and then select **Create Record**.</span></span> 
-   <span data-ttu-id="cee0c-211">새 **자원 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정되어 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="cee0c-211">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    -  <span data-ttu-id="cee0c-212">서비스: _sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="cee0c-212">Service: _sipfederationtls</span></span>
    -  <span data-ttu-id="cee0c-213">프로토콜: _tcp</span><span class="sxs-lookup"><span data-stu-id="cee0c-213">Protocol: _tcp</span></span>
    -  <span data-ttu-id="cee0c-214">우선 순위: 100</span><span class="sxs-lookup"><span data-stu-id="cee0c-214">Priority: 100</span></span>
    -  <span data-ttu-id="cee0c-215">가중치: 1</span><span class="sxs-lookup"><span data-stu-id="cee0c-215">Weight: 1</span></span>
    -  <span data-ttu-id="cee0c-216">포트: 5061</span><span class="sxs-lookup"><span data-stu-id="cee0c-216">Port: 5061</span></span>
    -  <span data-ttu-id="cee0c-217">대상(호스트 이름): sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cee0c-217">Target (Hostname): sipfed.online.lync.com</span></span>
-  <span data-ttu-id="cee0c-218">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-218">Select **OK**.</span></span> 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a><span data-ttu-id="cee0c-219">도메인이 없는 경우 레코드를 추가해 도메인을 소유하고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="cee0c-219">Add a record to verify that you own the domain, if you haven't already</span></span>
<span data-ttu-id="cee0c-220"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="cee0c-220"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="cee0c-221">DNS 레코드를 추가하여 도메인을 Microsoft 서비스 Microsoft는 사용자가 추가하는 도메인을 소유하고 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-221">Before you add the DNS records to set up your Microsoft services, Microsoft has to confirm that you own the domain you're adding.</span></span> <span data-ttu-id="cee0c-222">이렇게 하려면 다음 단계에 따라 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-222">To do this, you add a record, following the steps below.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cee0c-223">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-223">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> 
  

1. <span data-ttu-id="cee0c-224">Microsoft에서 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-224">Gather information from Microsoft.</span></span>  <br/> 
2. <span data-ttu-id="cee0c-225">I관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인</a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="cee0c-225">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span> 
3. <span data-ttu-id="cee0c-226">도메인 **페이지의** 확인 대상  도메인에 대한 작업 열에서 설정 **시작을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cee0c-226">On the **Domains** page, in the **Actions** column for the domain that you are verifying, select **Start setup**.</span></span> 
4. <span data-ttu-id="cee0c-227">**Microsoft에 도메인** 추가 페이지에서 시작 **1단계를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cee0c-227">On the **Add a domain to Microsoft** page, select **Start step 1**.</span></span> 
5. <span data-ttu-id="cee0c-228">도메인 **소유 확인** 페이지의 **이** 단계를 수행하기 위한 지침 참조 드롭다운 목록에서 일반 지침을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cee0c-228">On the **Confirm that you own your domain** page, in the **See instructions for performing this step with** drop-down list, choose **General instructions**.</span></span> 
6. <span data-ttu-id="cee0c-229">표에서 대상 또는 대상 주소 값을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-229">From the table, copy the Destination or Points to Address value.</span></span> <span data-ttu-id="cee0c-230">이 값은 다음 단계에서 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-230">You'll need it for the next step.</span></span> <span data-ttu-id="cee0c-231">모든 간격이 올바르게 유지되도록 이 값을 복사해서 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-231">We recommend copying and pasting this value, so that all of the spacing stays correct.</span></span>

<span data-ttu-id="cee0c-232">TXT 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-232">Add a TXT record.</span></span> 
-  <span data-ttu-id="cee0c-233">도메인의 DNS 관리자 페이지에서 작업  \> **텍스트(TXT)로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="cee0c-233">On the DNS Manager page for your domain, go to **Action** \> **Text (TXT)**.</span></span> 
-   <span data-ttu-id="cee0c-234">새 **자원 레코드 대화** 상자에서 편집 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cee0c-234">In the **New Resource Record** dialog box, select **Edit**.</span></span>  
-  <span data-ttu-id="cee0c-235">새 **리소스 레코드** 대화  상자의 사용자 지정 호스트 이름 영역에서 필드가 정확히 다음 값으로 설정되어 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="cee0c-235">In the **Custom Host Names** area of the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values.</span></span> 

> [!IMPORTANT] 
> <span data-ttu-id="cee0c-236">일부 Windows DNS 관리자에서는 txt 레코드를 만들 때 홈 이름이 기본적으로 상위 도메인으로 설정될 수 있도록 도메인이 설정되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-236">In some versions of Windows DNS Manager, the domain may have been set up so that when you create a txt record, the home name defaults to the parent domain.</span></span> <span data-ttu-id="cee0c-237">이 경우 TXT 레코드를 추가할 때 호스트 이름을 @ 또는 도메인 이름으로 설정하는 대신 비어 있음(값 없음)으로 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="cee0c-237">In this situation, when adding a TXT record, set the host name to blank (no value) instead of setting it to @ or the domain name.</span></span> 

- <span data-ttu-id="cee0c-238">호스트 이름: @</span><span class="sxs-lookup"><span data-stu-id="cee0c-238">Host Name: @</span></span>
- <span data-ttu-id="cee0c-239">유형: TXT</span><span class="sxs-lookup"><span data-stu-id="cee0c-239">Type: TXT</span></span>
- <span data-ttu-id="cee0c-240">주소: Microsoft에서 방금 복사한 대상 또는 대상 주소 값을 여기에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-240">Address: Paste the Destination or Points to Address value that you just copied from Microsoft here.</span></span>  
- <span data-ttu-id="cee0c-241">확인 **완료**  >  **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cee0c-241">Select **OK** > **Done**.</span></span>

<span data-ttu-id="cee0c-242">Microsoft에서 도메인을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-242">Verify your domain in Microsoft.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="cee0c-243">이렇게 하기 전에 15분 정도 기다렸다가 방금 만든 레코드가 인터넷을 통해 업데이트될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-243">Wait about 15 minutes before you do this, so the record you just created can update across the Internet.</span></span>       

- <span data-ttu-id="cee0c-244">Microsoft로 돌아가 아래 단계에 따라 확인 검사를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-244">Go back to Microsoft and follow the steps below to request a verification check.</span></span> <span data-ttu-id="cee0c-245">확인을 통해 이전 단계에 추가한 TXT 레코드를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-245">The check looks for the TXT record you added in the previous step.</span></span> <span data-ttu-id="cee0c-246">올바른 TXT 레코드가 발견되면 도메인이 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-246">When it finds the correct TXT record, the domain is verified.</span></span>  
1. <span data-ttu-id="cee0c-247">관리 센터에서 설치 도메인  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-247">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
2. <span data-ttu-id="cee0c-248">도메인 **페이지의** 확인 대상  도메인에 대한 작업 열에서 설정 **시작 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cee0c-248">On the **Domains** page, in the **Action** column for the domain you are verifying, select **Start setup**.</span></span> 
3. <span data-ttu-id="cee0c-249">도메인을 **소유하고** 있는지 확인 페이지에서 **완료를** 선택하고 지금 확인을 선택한 다음 확인 대화 상자에서 마친 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cee0c-249">On the **Confirm that you own your domain** page, select **done, verify now**, and then in the confirmation dialog box, select **Finish**.</span></span> 
   
> [!NOTE]
>  <span data-ttu-id="cee0c-p117">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cee0c-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a><span data-ttu-id="cee0c-253">온-프레미스 Active Directory에서 UPN으로 사용되는 라우팅할 수 없는 전자 메일 주소</span><span class="sxs-lookup"><span data-stu-id="cee0c-253">Non-routable email address used as a UPN in your on-prem Active Directory</span></span>
<span data-ttu-id="cee0c-254"><a name="BKMK_ADNote"> </a></span><span class="sxs-lookup"><span data-stu-id="cee0c-254"><a name="BKMK_ADNote"> </a></span></span>

<span data-ttu-id="cee0c-255">온-프레미스 Active Directory를 Microsoft와 동기화하려는 경우 active Directory UPN(사용자 계정 이름) 접미사는 유효한 도메인 접미사로, @contoso.local과 같은 지원되지 않는 도메인 접미사는 아닌지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cee0c-255">If you're planning to synchronize your on-premises Active Directory with Microsoft, you'll want to make sure that the Active Directory user principal name (UPN) suffix is a valid domain suffix, and not an unsupported domain suffix such as @contoso.local.</span></span> <span data-ttu-id="cee0c-256">UPN 접미어를 변경해야 하는 경우 디렉터리 동기화를 위해 라우팅할 수 없는 도메인을 [준비하는 방법을 참조합니다.](../../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="cee0c-256">If you need to change your UPN suffix, see [How to prepare a non-routable domain for directory synchronization](../../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="cee0c-p119">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cee0c-p119">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

## <a name="related-content"></a><span data-ttu-id="cee0c-260">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="cee0c-260">Related content</span></span>

<span data-ttu-id="cee0c-261">[Micrsoft 365에서](../get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host.md) 다른 호스트로 도메인 전송(문서)</span><span class="sxs-lookup"><span data-stu-id="cee0c-261">[Transfer a domain from Micrsoft 365 to another host](../get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host.md) (article)</span></span>\
<span data-ttu-id="cee0c-262">[사용자 Microsoft 365 도메인에서](../misc/pilot-microsoft-365-from-my-custom-domain.md) 파일럿 파일럿 시작(문서)</span><span class="sxs-lookup"><span data-stu-id="cee0c-262">[Pilot Microsoft 365 from my custom domain](../misc/pilot-microsoft-365-from-my-custom-domain.md) (article)</span></span>\
<span data-ttu-id="cee0c-263">[도메인 FAQ](../setup/domains-faq.yml) (문서)</span><span class="sxs-lookup"><span data-stu-id="cee0c-263">[Domains FAQ](../setup/domains-faq.yml) (article)</span></span>