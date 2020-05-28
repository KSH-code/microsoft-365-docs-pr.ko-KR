---
title: Windows 기반 DNS를 사용 하 여 Microsoft에 대 한 DNS 레코드 만들기
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: Microsoft의 Windows 기반 DNS에 있는 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대해 도메인을 확인 하 고 DNS 레코드를 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 8f65a397552813f22d4bde82f7fcd51c478d82bd
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400247"
---
# <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a><span data-ttu-id="06692-103">Windows 기반 DNS를 사용 하 여 Microsoft에 대 한 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="06692-103">Create DNS records for Microsoft using Windows-based DNS</span></span>

 <span data-ttu-id="06692-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="06692-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
   
<span data-ttu-id="06692-105">Windows 기반 DNS를 사용하여 자체 DNS 레코드를 호스트하는 경우 이 문서의 단계에 따라 전자 메일, 비즈니스용 Skype Online 등에 대한 레코드를 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="06692-105">If you host your own DNS records using Windows-based DNS, follow the steps in this article to set up your records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="06692-106">시작 하려면 업데이트할 수 있도록 [Windows 기반 dns에서 dns 레코드를 찾아야](#find-your-dns-records-in-windows-based-dns) 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-106">To get started, you need to [find your DNS records in Windows-based DNS](#find-your-dns-records-in-windows-based-dns) so you can update them.</span></span> <span data-ttu-id="06692-107">또한 온-프레미스 Active Directory를 Microsoft와 동기화 하려는 경우 [온-프레미스 Active directory에서 UPN으로 사용 되는 라우팅할 수 없는 전자 메일 주소](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="06692-107">Also, if you're planning to synchronize your on-premises Active Directory with Microsoft, see [Non-routable email address used as a UPN in your on-prem Active Directory](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory).</span></span>
  
<span data-ttu-id="06692-108">메일 흐름 문제 또는 기타 문제 DNS 레코드를 추가한 후에는 [도메인 이름 또는 DNS 레코드 변경 후 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="06692-108">Trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a><span data-ttu-id="06692-109">Windows 기반 DNS에서 DNS 레코드 찾기</span><span class="sxs-lookup"><span data-stu-id="06692-109">Find your DNS records in Windows-based DNS</span></span>
<span data-ttu-id="06692-110"><a name="BKMK_find_your_dns_1"> </a> 도메인에 대 한 DNS 레코드가 있는 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-110"><a name="BKMK_find_your_dns_1"> </a> Go to the page that has the DNS records for your domain.</span></span> <span data-ttu-id="06692-111">Windows Server 2008에서 작업 하는 경우 **시작**  >  **실행**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-111">If you're working in Windows Server 2008, go to **Start** > **Run**.</span></span> <span data-ttu-id="06692-112">Windows Server 2012에서 작업 하는 경우 Windows 키 및 **r**키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="06692-112">If you're working in Windows Server 2012, press the Windows key and **r**.</span></span> <span data-ttu-id="06692-113">**Dnsmgmnt.msc**를 입력 한 다음 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-113">Type **dnsmgmnt.msc**, and then select **OK**.</span></span> <span data-ttu-id="06692-114">DNS 관리자에서 \*\* \<DNS server name\> \> 정방향 조회 영역  \*\*을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-114">In DNS Manager, expand **\<DNS server name\>  \> Forward Lookup Zones**.</span></span> <span data-ttu-id="06692-115">도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-115">Select your domain.</span></span> <span data-ttu-id="06692-116">이제 DNS 레코드를 만들 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="06692-116">You're now ready to create the DNS records.</span></span>
   
## <a name="add-mx-record"></a><span data-ttu-id="06692-117">MX 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="06692-117">Add MX record</span></span>
<span data-ttu-id="06692-118"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="06692-118"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="06692-119">도메인에 대 한 전자 메일이 Microsoft에 제공 되도록 MX 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-119">Add an MX record so email for your domain will come to Microsoft.</span></span>
- <span data-ttu-id="06692-120">추가할 MX 레코드에는 mail.protection.outlook.com와 같이 표시 되는 값 ( **주소에 대 한 점수** 값)이 포함 됩니다 \<MX token\> . \<MX token\></span><span class="sxs-lookup"><span data-stu-id="06692-120">The MX record you'll add includes a value (the **Points to address** value) that looks something like this: \<MX token\>.mail.protection.outlook.com, where \<MX token\> is a value like MSxxxxxxx.</span></span> 
- <span data-ttu-id="06692-121">Microsoft의 DNS 레코드 추가 페이지에서 Exchange Online 섹션의 MX 행에서 Points to address에 나열 된 값을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-121">From the MX row in the Exchange Online section of the Add DNS records page in Microsoft, copy the value listed under Points to address.</span></span> <span data-ttu-id="06692-122">이 값은이 작업에서 만드는 레코드에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06692-122">You'll use this value in the record you're creating in this task.</span></span> 
- <span data-ttu-id="06692-123">도메인의 DNS 관리자 페이지에서 **동작**  >  **MX (메일 교환기)** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-123">On the DNS Manager page for the domain, go to **Action** > **Mail Exchanger (MX)**.</span></span> <span data-ttu-id="06692-124">해당 도메인의이 페이지를 찾으려면 [Windows 기반 dns에서 dns 레코드 찾기를](#find-your-dns-records-in-windows-based-dns)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="06692-124">To find this page for the domain, see [Find your DNS records in Windows-based DNS](#find-your-dns-records-in-windows-based-dns).</span></span>  
- <span data-ttu-id="06692-125">**새 리소스 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-125">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span> 
    - <span data-ttu-id="06692-126">호스트 이름: </span><span class="sxs-lookup"><span data-stu-id="06692-126">Host Name:</span></span> 
    - <span data-ttu-id="06692-127">@Address: Microsoft에서 방금 복사한 점수 값을 여기에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="06692-127">@Address: Paste the Points to address  value that you just copied from Microsoft here.</span></span>  
    - <span data-ttu-id="06692-128">우선</span><span class="sxs-lookup"><span data-stu-id="06692-128">Pref:</span></span> 
- <span data-ttu-id="06692-129">**변경 내용 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-129">Select **Save Changes**.</span></span>
- <span data-ttu-id="06692-130">사용되지 않는 MX 레코드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-130">Remove any obsolete MX records.</span></span> <span data-ttu-id="06692-131">다른 곳에서 전자 메일을 라우팅하는이 도메인에 대 한 오래 된 MX 레코드가 있는 경우에는 각 이전 레코드 옆의 확인란을 선택 하 고 확인 **삭제**를 선택  >  **OK**합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-131">If you have any old MX records for this domain that route email somewhere else, select the check box next to each old record, and then select **Delete** > **OK**.</span></span> 
   
## <a name="add-cname-records"></a><span data-ttu-id="06692-132">CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="06692-132">Add CNAME records</span></span>
<span data-ttu-id="06692-133"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="06692-133"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="06692-134">Microsoft에 필요한 CNAME 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-134">Add the CNAME records that are required for Microsoft.</span></span> <span data-ttu-id="06692-135">Microsoft에 추가 CNAME 레코드가 나열 되 면 여기에 표시 된 것과 동일한 일반적인 단계에 따라 해당 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-135">If additional CNAME records are listed in Microsoft, add those following the same general steps shown here.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="06692-136">Microsoft 용 MDM (모바일 장치 관리)이 있는 경우 두 개의 CNAME 레코드를 추가로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-136">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="06692-137">다른 4개의 CNAME 레코드를 만드는 데 사용한 절차를 따르되 다음 표의 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-137">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="06692-138">(MDM이 없는 경우에는이 단계를 건너뛰어도 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="06692-138">(If you do not have MDM, you can skip this step.)</span></span> 

- <span data-ttu-id="06692-139">도메인의 DNS 관리자 페이지에서 **작업**  >  **cname (cname)** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-139">On the DNS Manager page for the domain, go to **Action** > **CNAME (CNAME)**.</span></span>
- <span data-ttu-id="06692-140">**새 리소스 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-140">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="06692-141">호스트 이름: 자동 검색</span><span class="sxs-lookup"><span data-stu-id="06692-141">Host Name: autodiscover</span></span>
    - <span data-ttu-id="06692-142">형식일</span><span class="sxs-lookup"><span data-stu-id="06692-142">Type:</span></span> 
    - <span data-ttu-id="06692-143">CNAMEAddress: autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="06692-143">CNAMEAddress: autodiscover.outlook.com</span></span>
- <span data-ttu-id="06692-144">**O**K를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-144">Select **O**K.</span></span>

<span data-ttu-id="06692-145">SIP CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-145">Add the SIP CNAME record.</span></span> 
- <span data-ttu-id="06692-146">도메인의 DNS 관리자 페이지에서 **작업** \> **cname (cname)** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-146">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
- <span data-ttu-id="06692-147">**새 리소스 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-147">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="06692-148">호스트 이름: sip</span><span class="sxs-lookup"><span data-stu-id="06692-148">Host Name: sip</span></span>
    - <span data-ttu-id="06692-149">유형: CNAME</span><span class="sxs-lookup"><span data-stu-id="06692-149">Type: CNAME</span></span>
    - <span data-ttu-id="06692-150">주소: sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="06692-150">Address: sipdir.online.lync.com</span></span>
- <span data-ttu-id="06692-151">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-151">Select **OK**.</span></span>

<span data-ttu-id="06692-152">비즈니스용 Skype Online 자동 검색 CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-152">Add the Skype for Business Online Autodiscover CNAME record.</span></span>  
- <span data-ttu-id="06692-153">도메인의 DNS 관리자 페이지에서 **작업** \> **cname (cname)** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-153">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> <span data-ttu-id="06692-154">**새 리소스 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-154">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="06692-155">호스트 이름: lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="06692-155">Host Name: lyncdiscover</span></span>
    - <span data-ttu-id="06692-156">유형: CNAME</span><span class="sxs-lookup"><span data-stu-id="06692-156">Type: CNAME</span></span>
    - <span data-ttu-id="06692-157">주소: webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="06692-157">Address: webdir.online.lync.com</span></span>
- <span data-ttu-id="06692-158">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-158">Select **OK**.</span></span>
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft"></a><span data-ttu-id="06692-159">Microsoft 용 MDM (모바일 장치 관리)에 대 한 두 개의 CNAME 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="06692-159">Add two CNAME records for Mobile Device Management (MDM) for Microsoft</span></span>

> [!IMPORTANT]
> <span data-ttu-id="06692-160">Microsoft 용 MDM (모바일 장치 관리)이 있는 경우 두 개의 CNAME 레코드를 추가로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-160">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="06692-161">다른 4개의 CNAME 레코드를 만드는 데 사용한 절차를 따르되 다음 표의 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-161">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="06692-162">> (MDM이 없는 경우이 단계를 건너뛸 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="06692-162">>(If you do not have MDM, you can skip this step.)</span></span> 
  

<span data-ttu-id="06692-163">MDM Enterpriseregistration CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-163">Add the MDM Enterpriseregistration CNAME record.</span></span>  
- <span data-ttu-id="06692-164">도메인의 DNS 관리자 페이지에서 **작업** \> **cname (cname)** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-164">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
- <span data-ttu-id="06692-165">**새 리소스 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-165">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
- <span data-ttu-id="06692-166">호스트 이름: enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="06692-166">Host Name: enterpriseregistration</span></span>
- <span data-ttu-id="06692-167">유형: CNAME</span><span class="sxs-lookup"><span data-stu-id="06692-167">Type: CNAME</span></span>
- <span data-ttu-id="06692-168">주소: enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="06692-168">Address: enterpriseregistration.windows.net</span></span>
- <span data-ttu-id="06692-169">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-169">Select **OK**.</span></span> 

<span data-ttu-id="06692-170">MDM Enterpriseenrollment CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-170">Add the MDM Enterpriseenrollment CNAME record.</span></span> 
-  <span data-ttu-id="06692-171">도메인의 DNS 관리자 페이지에서 **작업** \> **cname (cname)** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-171">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
-  <span data-ttu-id="06692-172">**새 리소스 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-172">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="06692-173">호스트 이름: enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="06692-173">Host Name: enterpriseenrollment</span></span>
    - <span data-ttu-id="06692-174">유형: CNAME</span><span class="sxs-lookup"><span data-stu-id="06692-174">Type: CNAME</span></span>
    - <span data-ttu-id="06692-175">주소: enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="06692-175">Address: enterpriseenrollment-s.manage.microsoft.com</span></span>
- <span data-ttu-id="06692-176">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-176">Select **OK**.</span></span>
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="06692-177">전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="06692-177">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="06692-178"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="06692-178"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="06692-179">도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06692-179">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="06692-180">도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06692-180">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="06692-181">도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="06692-181">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="06692-182">대신, 두 값 집합을 모두 포함 하는 *단일* SPF 레코드가 있도록 현재 레코드에 필수 Microsoft 값을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-182">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="06692-183">스팸 메일을 방지하는 데 도움이 되도록 도메인의 SPF TXT 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-183">Add the SPF TXT record for your domain to help prevent email spam.</span></span>
  
- <span data-ttu-id="06692-p111">이 레코드의 TXT 값에 마케팅 전자 메일의 문자열과 같은 다른 문자열이 이미 있을 수 있습니다. 이 경우 해당 문자열은 그대로 두고 이 문자열을 큰따옴표로 구분하여 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-p111">You might already have other strings in the TXT value for this record (such as strings for marketing email), which is fine. Leave those strings in place and add this one, placing double-quotes around each string to separate them.</span></span> 
- <span data-ttu-id="06692-186">도메인의 DNS 관리자 페이지에서 **동작** \> **텍스트 (TXT)** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-186">On the DNS Manager page for your domain, go to **Action** \> **Text (TXT)**.</span></span> 
-  <span data-ttu-id="06692-187">**새 리소스 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-187">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values.</span></span> 
 > [!IMPORTANT]
> <span data-ttu-id="06692-188">일부 Windows DNS 관리자 버전에서는 txt 레코드를 만들 때 홈 이름이 기본적으로 상위 도메인이 되는 것으로 도메인을 설정 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06692-188">In some versions of Windows DNS Manager, the domain may have been set up so that when you create a txt record, the home name defaults to the parent domain.</span></span> <span data-ttu-id="06692-189">이 경우 TXT 레코드를 추가할 때 호스트 이름을 @ 또는 도메인 이름으로 설정하는 대신 비어 있음(값 없음)으로 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="06692-189">In this situation, when adding a TXT record, set the host name to blank (no value) instead of setting it to @ or the domain name.</span></span> 

-  <span data-ttu-id="06692-190">호스트 유형: @</span><span class="sxs-lookup"><span data-stu-id="06692-190">Host type: @</span></span>
-  <span data-ttu-id="06692-191">레코드 유형: TXT</span><span class="sxs-lookup"><span data-stu-id="06692-191">Record Type: TXT</span></span>
-  <span data-ttu-id="06692-192">주소: v = spf1에는:</span><span class="sxs-lookup"><span data-stu-id="06692-192">Address: v=spf1 include:spf.protection.outlook.com -all</span></span> 
         
-  <span data-ttu-id="06692-193">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-193">Select **OK**.</span></span>
   
## <a name="add-srv-records"></a><span data-ttu-id="06692-194">SRV 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="06692-194">Add SRV records</span></span>
<span data-ttu-id="06692-195"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="06692-195"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="06692-196">Microsoft에 필요한 두 개의 SRV 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-196">Add the two SRV records that are required for Microsoft.</span></span>

<span data-ttu-id="06692-197">비즈니스용 Skype Online 웹 회의에 대한 SIP SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-197">Add the SIP SRV record for Skype for Business Online web conferencing.</span></span>  <br/> 
-  <span data-ttu-id="06692-198">도메인의 DNS 관리자 페이지에서 **Action** \> **다른 새 레코드**작업으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-198">On the DNS Manager page for your domain, go to **Action** \> **Other New Records**.</span></span> 
-   <span data-ttu-id="06692-199">**리소스 레코드 종류** 창에서 **서비스 위치 (SRV)** 를 선택한 다음 **레코드 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-199">In the **Resource Record Type** window, select **Service Location (SRV)**, and then select **Create Record**.</span></span> 
-   <span data-ttu-id="06692-200">**새 리소스 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-200">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    -  <span data-ttu-id="06692-201">서비스: _sip</span><span class="sxs-lookup"><span data-stu-id="06692-201">Service: _sip</span></span>
    -  <span data-ttu-id="06692-202">프로토콜: _tls</span><span class="sxs-lookup"><span data-stu-id="06692-202">Protocol: _tls</span></span>
    -  <span data-ttu-id="06692-203">우선 순위: 100</span><span class="sxs-lookup"><span data-stu-id="06692-203">Priority: 100</span></span>
    -  <span data-ttu-id="06692-204">가중치: 1</span><span class="sxs-lookup"><span data-stu-id="06692-204">Weight: 1</span></span>
    -  <span data-ttu-id="06692-205">포트: 443</span><span class="sxs-lookup"><span data-stu-id="06692-205">Port: 443</span></span>
    -  <span data-ttu-id="06692-206">대상 (호스트 이름): sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="06692-206">Target (Hostname): sipdir.online.lync.com</span></span>
-  <span data-ttu-id="06692-207">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-207">Select **OK**.</span></span> 


<span data-ttu-id="06692-208">비즈니스용 Skype Online 페더레이션에 대한 SIP SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-208">Add the SIP SRV record for Skype for Business Online federation.</span></span>  
-  <span data-ttu-id="06692-209">도메인의 DNS 관리자 페이지에서 **Action** \> **다른 새 레코드**작업으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-209">On the DNS Manager page for your domain, go to **Action** \> **Other New Records**.</span></span>  
-  <span data-ttu-id="06692-210">**리소스 레코드 종류** 창에서 **서비스 위치 (SRV)** 를 선택한 다음 **레코드 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-210">In the **Resource Record Type** window, select **Service Location (SRV)**, and then select **Create Record**.</span></span> 
-   <span data-ttu-id="06692-211">**새 리소스 레코드** 대화 상자에서 필드가 정확히 다음 값으로 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-211">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    -  <span data-ttu-id="06692-212">서비스: _sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="06692-212">Service: _sipfederationtls</span></span>
    -  <span data-ttu-id="06692-213">프로토콜: _tcp</span><span class="sxs-lookup"><span data-stu-id="06692-213">Protocol: _tcp</span></span>
    -  <span data-ttu-id="06692-214">우선 순위: 100</span><span class="sxs-lookup"><span data-stu-id="06692-214">Priority: 100</span></span>
    -  <span data-ttu-id="06692-215">가중치: 1</span><span class="sxs-lookup"><span data-stu-id="06692-215">Weight: 1</span></span>
    -  <span data-ttu-id="06692-216">포트: 5061</span><span class="sxs-lookup"><span data-stu-id="06692-216">Port: 5061</span></span>
    -  <span data-ttu-id="06692-217">대상 (호스트 이름): sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="06692-217">Target (Hostname): sipfed.online.lync.com</span></span>
-  <span data-ttu-id="06692-218">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-218">Select **OK**.</span></span> 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a><span data-ttu-id="06692-219">도메인이 없는 경우 레코드를 추가해 도메인을 소유하고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="06692-219">Add a record to verify that you own the domain, if you haven't already</span></span>
<span data-ttu-id="06692-220"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="06692-220"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="06692-221">Microsoft 서비스를 설정 하기 위해 DNS 레코드를 추가 하기 전에 추가 중인 도메인을 소유 하 고 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-221">Before you add the DNS records to set up your Microsoft services, Microsoft has to confirm that you own the domain you're adding.</span></span> <span data-ttu-id="06692-222">이렇게 하려면 다음 단계에 따라 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-222">To do this, you add a record, following the steps below.</span></span>
  
> [!NOTE]
> <span data-ttu-id="06692-223">이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06692-223">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> 
  

1. <span data-ttu-id="06692-224">Microsoft에서 정보를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-224">Gather information from Microsoft.</span></span>  <br/> 
2. <span data-ttu-id="06692-225">I관리 센터에서 \*\* 설정 \*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="06692-225">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span> 
3. <span data-ttu-id="06692-226">**도메인** 페이지의 확인 하려는 도메인에 대 한 **작업** 열에서 **설정 시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-226">On the **Domains** page, in the **Actions** column for the domain that you are verifying, select **Start setup**.</span></span> 
4. <span data-ttu-id="06692-227">**Microsoft에 도메인 추가** 페이지에서 **1 단계 시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-227">On the **Add a domain to Microsoft** page, select **Start step 1**.</span></span> 
5. <span data-ttu-id="06692-228">사용자의 **도메인을 소유 하** 고 있는지 확인 페이지의 **이 단계를 수행 하기 위한 지침 보기** 드롭다운 목록에서 **일반 지침**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-228">On the **Confirm that you own your domain** page, in the **See instructions for performing this step with** drop-down list, choose **General instructions**.</span></span> 
6. <span data-ttu-id="06692-229">표에서 대상 또는 대상 주소 값을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-229">From the table, copy the Destination or Points to Address value.</span></span> <span data-ttu-id="06692-230">이 값은 다음 단계에서 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-230">You'll need it for the next step.</span></span> <span data-ttu-id="06692-231">모든 간격이 올바르게 유지되도록 이 값을 복사해서 붙여 넣는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="06692-231">We recommend copying and pasting this value, so that all of the spacing stays correct.</span></span>

<span data-ttu-id="06692-232">TXT 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-232">Add a TXT record.</span></span> 
-  <span data-ttu-id="06692-233">도메인의 DNS 관리자 페이지에서 **동작** \> **텍스트 (TXT)** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-233">On the DNS Manager page for your domain, go to **Action** \> **Text (TXT)**.</span></span> 
-   <span data-ttu-id="06692-234">**새 리소스 레코드** 대화 상자에서 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-234">In the **New Resource Record** dialog box, select **Edit**.</span></span>  
-  <span data-ttu-id="06692-235">**새 리소스 레코드** 대화 상자의 **사용자 지정 호스트 이름** 영역에서 필드가 정확히 다음 값으로 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-235">In the **Custom Host Names** area of the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values.</span></span> 

> [!IMPORTANT] 
> <span data-ttu-id="06692-236">일부 Windows DNS 관리자 버전에서는 txt 레코드를 만들 때 홈 이름이 기본적으로 상위 도메인이 되는 것으로 도메인을 설정 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06692-236">In some versions of Windows DNS Manager, the domain may have been set up so that when you create a txt record, the home name defaults to the parent domain.</span></span> <span data-ttu-id="06692-237">이 경우 TXT 레코드를 추가할 때 호스트 이름을 @ 또는 도메인 이름으로 설정하는 대신 비어 있음(값 없음)으로 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="06692-237">In this situation, when adding a TXT record, set the host name to blank (no value) instead of setting it to @ or the domain name.</span></span> 

- <span data-ttu-id="06692-238">호스트 이름: @</span><span class="sxs-lookup"><span data-stu-id="06692-238">Host Name: @</span></span>
- <span data-ttu-id="06692-239">문자: TXT</span><span class="sxs-lookup"><span data-stu-id="06692-239">Type: TXT</span></span>
- <span data-ttu-id="06692-240">주소: 지금 Microsoft에서 복사한 대상 또는 주소 값을 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="06692-240">Address: Paste the Destination or Points to Address value that you just copied from Microsoft here.</span></span>  
- <span data-ttu-id="06692-241">**확인**  >  **완료**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-241">Select **OK** > **Done**.</span></span>

<span data-ttu-id="06692-242">Microsoft에서 도메인을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-242">Verify your domain in Microsoft.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="06692-243">이 작업을 수행 하기 전에 15 분 정도 기다린 후 방금 만든 레코드가 인터넷을 통해 업데이트 될 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-243">Wait about 15 minutes before you do this, so the record you just created can update across the Internet.</span></span>       

- <span data-ttu-id="06692-244">Microsoft로 돌아가서 아래 단계에 따라 확인을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-244">Go back to Microsoft and follow the steps below to request a verification check.</span></span> <span data-ttu-id="06692-245">확인을 통해 이전 단계에 추가한 TXT 레코드를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="06692-245">The check looks for the TXT record you added in the previous step.</span></span> <span data-ttu-id="06692-246">올바른 TXT 레코드가 발견되면 도메인이 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="06692-246">When it finds the correct TXT record, the domain is verified.</span></span>  
1. <span data-ttu-id="06692-247">관리 센터에서 **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 설정 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-247">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
2. <span data-ttu-id="06692-248">**도메인** 페이지의 확인 하려는 도메인에 대 한 **작업** 열에서 **설정 시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-248">On the **Domains** page, in the **Action** column for the domain you are verifying, select **Start setup**.</span></span> 
3. <span data-ttu-id="06692-249">사용자의 **도메인 소유 여부 확인** 페이지에서 **완료, 지금 확인**을 차례로 선택 하 고 확인 대화 상자에서 **마침을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06692-249">On the **Confirm that you own your domain** page, select **done, verify now**, and then in the confirmation dialog box, select **Finish**.</span></span> 
   
> [!NOTE]
>  <span data-ttu-id="06692-p117">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06692-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a><span data-ttu-id="06692-253">온-프레미스 Active Directory에서 UPN으로 사용되는 라우팅할 수 없는 전자 메일 주소</span><span class="sxs-lookup"><span data-stu-id="06692-253">Non-routable email address used as a UPN in your on-prem Active Directory</span></span>
<span data-ttu-id="06692-254"><a name="BKMK_ADNote"> </a></span><span class="sxs-lookup"><span data-stu-id="06692-254"><a name="BKMK_ADNote"> </a></span></span>

<span data-ttu-id="06692-255">온-프레미스 Active Directory를 Microsoft와 동기화 하려는 경우 Active Directory UPN (사용자 계정 이름) 접미사가 유효한 도메인 접미사 인지 확인 하 고 @contoso와 같은 지원 되지 않는 도메인 접미사를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="06692-255">If you're planning to synchronize your on-premises Active Directory with Microsoft, you'll want to make sure that the Active Directory user principal name (UPN) suffix is a valid domain suffix, and not an unsupported domain suffix such as @contoso.local.</span></span> <span data-ttu-id="06692-256">UPN 접미사를 변경 해야 하는 경우 [디렉터리 동기화를 위해 라우팅할 수 없는 도메인을 준비](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization)하는 방법을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="06692-256">If you need to change your UPN suffix, see [How to prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="06692-p119">일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06692-p119">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
