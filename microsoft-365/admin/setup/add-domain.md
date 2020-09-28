---
title: Microsoft 365에 도메인 추가
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
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: DNS 호스트에서 DNS 레코드를 추가 하 여 Microsoft 365 관리 센터에서 Microsoft 365에 도메인을 추가 합니다. 설치 마법사가 프로세스를 안내 합니다.
ms.openlocfilehash: 09a66b9ac4f97a076d71dd7f259678181378ae48
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295025"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="a34f4-104">Microsoft 365에 도메인 추가</span><span class="sxs-lookup"><span data-stu-id="a34f4-104">Add a domain to Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="a34f4-105">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-105">The admin center is changing.</span></span> <span data-ttu-id="a34f4-106">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a34f4-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

 <span data-ttu-id="a34f4-107">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="a34f4-107">**[Check the Domains FAQ](domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="a34f4-108">*도메인을 추가, 수정 또는 제거 하려면 [비즈니스 또는 기업 계획](https://products.office.com/business/office)의 **전역 관리자** **여야 합니다** . 이러한 변경 내용은 전체 테 넌 트에 영향을 미치며 *사용자 지정 된 관리자* 또는 *일반 사용자* 는 이러한 변경 작업을 수행할 수 없습니다.*</span><span class="sxs-lookup"><span data-stu-id="a34f4-108">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="a34f4-109">도메인을 추가, 설정 또는 계속 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-109">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a34f4-110"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="a34f4-111"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-111">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a34f4-112"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="a34f4-113">**설정**  >  **도메인** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-113">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="a34f4-114">**도메인 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-114">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="a34f4-115">추가 하려는 도메인의 이름을 입력 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-115">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="a34f4-116">도메인을 소유 하 고 있는지 확인 하는 방법을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-116">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="a34f4-117">도메인 등록 기관에서 [도메인 연결](#domain-connect-registrars-integrating-with-microsoft-365)을 사용 하는 경우 microsoft는 등록자에 로그인 하 고 microsoft 365에 대 한 연결을 확인 하 여 [레코드를 자동으로 설정](../get-help-with-domains/domain-connect.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-117">If your domain registrar uses [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span> <span data-ttu-id="a34f4-118">관리자 센터로 반환 되 고 Microsoft는 도메인을 자동으로 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-118">You'll be returned to the admin center and Microsoft will then automatically verify your domain.</span></span>
    2. <span data-ttu-id="a34f4-119">TXT 레코드를 사용하여 도메인을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-119">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="a34f4-120">이를 선택 하 고 **다음** 을 선택 하 여 등록자의 웹 사이트에이 DNS 레코드를 추가 하는 방법에 대 한 지침을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-120">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="a34f4-121">이 작업은 레코드를 추가한 후 확인 하는 데 최대 30 분까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-121">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    3. <span data-ttu-id="a34f4-122">텍스트 파일을 도메인의 웹 사이트에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-122">You can add a text file to your domain's website.</span></span> <span data-ttu-id="a34f4-123">설치 마법사에서 .txt 파일을 선택 하 여 다운로드 한 다음 웹 사이트의 최상위 폴더에 파일을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-123">Select and download the .txt file from the setup wizard, then upload the file to your website's top level folder.</span></span> <span data-ttu-id="a34f4-124">파일의 경로는 다음과 같이 표시 됩니다 `http://mydomain.com/ms39978200.txt` .</span><span class="sxs-lookup"><span data-stu-id="a34f4-124">The path to the file should look similar to: `http://mydomain.com/ms39978200.txt`.</span></span> <span data-ttu-id="a34f4-125">웹 사이트에서 해당 파일을 찾아 도메인을 소유 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-125">We'll confirm you own the domain by finding the file on your website.</span></span>
    
6. <span data-ttu-id="a34f4-126">Microsoft에서 도메인을 사용 하는 데 필요한 DNS 변경 작업을 수행 하는 방법을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-126">Choose how you want to make the DNS changes required for Microsoft to use your domain.</span></span>
    
    1. <span data-ttu-id="a34f4-127">**DNS 레코드 추가** 선택 등록자 등록 자가 [도메인 연결](#domain-connect-registrars-integrating-with-microsoft-365)을 지 원하는 경우 microsoft에서는 등록자에 로그인 하 고 microsoft 365에 대 한 연결을 확인 하 여 [레코드를 자동으로 설정](../get-help-with-domains/domain-connect.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-127">Choose **Add the DNS records for me** if your registrar supports [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span>
    2. <span data-ttu-id="a34f4-128">특정 Microsoft 365 서비스만 도메인에 연결 하거나 지금이를 건너뛰고 나중에이 작업을 수행 하려는 경우에 **는 직접 DNS 레코드를 추가** 합니다 .를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-128">Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="a34f4-129">**무엇을 할지 정확히 아는 경우에만 이 옵션을 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="a34f4-129">**Choose this option if you know exactly what you're doing.**</span></span>

7. <span data-ttu-id="a34f4-130">*DNS 레코드를 직접 추가* 하도록 선택한 경우에는 **다음** 을 선택 하 고 도메인을 설정 하기 위해 등록 기관 웹 사이트에 추가 해야 하는 모든 레코드가 포함 된 페이지를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-130">If you chose to *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 

    <span data-ttu-id="a34f4-131">포털에서 등록 기관을 인식하지 못하는 경우에는 [이러한 일반 지침을 따르면](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-131">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="a34f4-132">호스트를 찾으려면 [호스트 별 지침](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) 목록을 확인하고 다음 단계에 따라 필요한 모든 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-132">Check our list of [host-specific instructions](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="a34f4-133">사용 중인 도메인의 DNS 호스팅 공급자 또는 도메인 등록 기관을 모르는 경우 [도메인 등록자 또는 DNS 호스팅 공급자 찾기](../get-help-with-domains/find-your-domain-registrar.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a34f4-133">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="a34f4-134">나중에 대기 하려면 모든 서비스의 선택을 취소 하 고 **계속**을 클릭 하거나 이전 도메인 연결 단계에서 **다른 옵션** 을 선택 하 고 **지금은 건너뛰기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-134">If you want to wait for later, either unselect all the services and click **Continue**, or in the previous domain connection step choose **More Options** and select **Skip this for now**.</span></span>
    
8. <span data-ttu-id="a34f4-135">**완료** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-135">Select **Finish** - you're done!</span></span>

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="a34f4-136">사용자 지정 DNS 레코드 추가 또는 편집</span><span class="sxs-lookup"><span data-stu-id="a34f4-136">Add or edit custom DNS records</span></span>

<span data-ttu-id="a34f4-137">아래 단계에 따라 웹 사이트 또는 타사 서비스에 대 한 사용자 지정 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-137">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="a34f4-138">에서 Microsoft 관리 센터에 로그인 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-138">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="a34f4-139">**설정**   >  **도메인** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-139">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="a34f4-140">**도메인** 페이지에서 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-140">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="a34f4-141">**DNS 설정**에서 **사용자 지정 레코드**를 선택 합니다. 그런 다음 **새 사용자 지정 레코드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-141">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="a34f4-142">추가할 DNS 레코드 유형을 선택 하 고 새 레코드에 대 한 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-142">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="a34f4-143">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-143">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="a34f4-144">도메인 연결을 사용 하는 등록 기관</span><span class="sxs-lookup"><span data-stu-id="a34f4-144">Registrars with Domain Connect</span></span>

<span data-ttu-id="a34f4-145">[도메인 연결](https://www.domainconnect.org/) 사용 등록 기관는 3 단계 프로세스에서 분 단위로 Microsoft 365에 도메인을 추가할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-145">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="a34f4-146">이 마법사에서는 도메인을 소유 하 고 있는지 확인 하 고, 사용자의 도메인 레코드를 자동으로 설정 하 여 전자 메일이 Microsoft 365 및 기타 Microsoft 365 서비스 (예를 들어, 사용자의 도메인으로 작업)를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-146">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a34f4-147">설정 마법사를 시작하기 전에 브라우저의 팝업 차단 기능을 해제하세요.</span><span class="sxs-lookup"><span data-stu-id="a34f4-147">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="a34f4-148">도메인 연결 등록 기관 Microsoft 365 통합</span><span class="sxs-lookup"><span data-stu-id="a34f4-148">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="a34f4-149">1 &amp; 1gb 이상 os</span><span class="sxs-lookup"><span data-stu-id="a34f4-149">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="a34f4-150">EuroDNS</span><span class="sxs-lookup"><span data-stu-id="a34f4-150">EuroDNS</span></span>](https://www.eurodns.com/)
- [<span data-ttu-id="a34f4-151">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="a34f4-151">Cloudflare</span></span>](https://www.cloudflare.com/)
- [<span data-ttu-id="a34f4-152">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="a34f4-152">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="a34f4-153">WordPress.com</span><span class="sxs-lookup"><span data-stu-id="a34f4-153">WordPress.com</span></span>](https://wordpress.com/)
- [<span data-ttu-id="a34f4-154">Plesk</span><span class="sxs-lookup"><span data-stu-id="a34f4-154">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="a34f4-155">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="a34f4-155">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="a34f4-156">SecureServer 또는 WildWestDomains (SecureServer DNS 호스팅을 사용 하는 GoDaddy 리셀러)</span><span class="sxs-lookup"><span data-stu-id="a34f4-156">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - <span data-ttu-id="a34f4-157">예제:</span><span class="sxs-lookup"><span data-stu-id="a34f4-157">Examples:</span></span>
        - [<span data-ttu-id="a34f4-158">DomainsPricedRight</span><span class="sxs-lookup"><span data-stu-id="a34f4-158">DomainsPricedRight</span></span>](https://www.domainspricedright.com/products/domain-registration)
        - [<span data-ttu-id="a34f4-159">지금 domainright</span><span class="sxs-lookup"><span data-stu-id="a34f4-159">DomainRightNow</span></span>](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="a34f4-160">전자 메일 및 웹 사이트는 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="a34f4-160">What happens to my email and website?</span></span>

<span data-ttu-id="a34f4-161">설치를 마친 후에는 도메인에 대 한 MX 레코드가 Microsoft 365를 가리키도록 업데이트 되 고 도메인의 모든 전자 메일이 Microsoft 365로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-161">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="a34f4-162">도메인에 전자 메일을 보내는 모든 사용자에 대해 사용자를 추가 하 고 Microsoft 365에 사서함을 설정 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-162">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="a34f4-163">업무에 사용하는 웹 사이트가 있는 경우 어디에 있든 작동이 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-163">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="a34f4-164">도메인 연결 설정 단계는 웹 사이트에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a34f4-164">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="a34f4-165">관련 문서</span><span class="sxs-lookup"><span data-stu-id="a34f4-165">Related articles</span></span>

[<span data-ttu-id="a34f4-166">도메인 FAQ</span><span class="sxs-lookup"><span data-stu-id="a34f4-166">Domains FAQ</span></span>](domains-faq.md)

[<span data-ttu-id="a34f4-167">도메인이 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="a34f4-167">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="a34f4-168">Microsoft 365에서 도메인 이름 구입하기</span><span class="sxs-lookup"><span data-stu-id="a34f4-168">Buy a domain name in Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="a34f4-169">도메인 설정(호스트별 지침)</span><span class="sxs-lookup"><span data-stu-id="a34f4-169">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)
