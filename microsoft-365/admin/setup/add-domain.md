---
title: Microsoft 365에 도메인 추가
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
description: DNS 호스트에 DNS 레코드를 추가하여 Microsoft 365 관리 센터의 Microsoft 365에 도메인을 추가합니다. 설치 마법사가 프로세스를 안내합니다.
ms.openlocfilehash: 5a3c86fb2b2f93e9da844c15a55555c5d0d7b5c1
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114264"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="daa75-104">Microsoft 365에 도메인 추가</span><span class="sxs-lookup"><span data-stu-id="daa75-104">Add a domain to Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="daa75-105">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daa75-105">The admin center is changing.</span></span> <span data-ttu-id="daa75-106">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="daa75-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

 <span data-ttu-id="daa75-107">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](domains-faq.yml)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="daa75-107">**[Check the Domains FAQ](domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="daa75-108">*도메인을 추가, 수정 또는  제거하려면  비즈니스 또는 엔터프라이즈 계획의 전역 관리자 [되어야 합니다.](https://products.office.com/business/office) 이러한 변경 내용은 전체 테넌트,   사용자 지정된 관리자 또는 일반 사용자에게 영향을 미치며 이러한 변경은 할 수 없습니다.*</span><span class="sxs-lookup"><span data-stu-id="daa75-108">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="daa75-109">다음 단계에 따라 도메인을 추가, 설정 또는 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="daa75-109">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="daa75-110"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="daa75-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="daa75-111"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="daa75-111">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="daa75-112"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="daa75-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="daa75-113">설정 도메인   >  **페이지로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="daa75-113">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="daa75-114">도메인 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="daa75-114">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="daa75-115">추가할 도메인의 이름을 입력하고 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="daa75-115">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="daa75-116">도메인을 소유하고 있는지 확인하는 방법을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="daa75-116">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="daa75-117">도메인 등록 기관에서 [Domain Connect를](#domain-connect-registrars-integrating-with-microsoft-365)사용하는 경우 [Microsoft는](../get-help-with-domains/domain-connect.md) 사용자가 등록 기관에 로그인하고 Microsoft 365에 대한 연결을 확인하여 레코드를 자동으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="daa75-117">If your domain registrar uses [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span> <span data-ttu-id="daa75-118">You'll be returned to the admin center and Microsoft will automatically verify your domain.</span><span class="sxs-lookup"><span data-stu-id="daa75-118">You'll be returned to the admin center and Microsoft will then automatically verify your domain.</span></span>
    2. <span data-ttu-id="daa75-119">TXT 레코드를 사용하여 도메인을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daa75-119">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="daa75-120">이 옵션을 선택하고 **다음을** 선택하여 등록 기관의 웹 사이트에 이 DNS 레코드를 추가하는 방법에 대한 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="daa75-120">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="daa75-121">레코드를 추가한 후 확인하는 데 최대 30분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daa75-121">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    3. <span data-ttu-id="daa75-122">텍스트 파일을 도메인의 웹 사이트에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daa75-122">You can add a text file to your domain's website.</span></span> <span data-ttu-id="daa75-123">설치 마법사에서 .txt 파일을 선택하고 다운로드한 다음 웹 사이트의 최상위 폴더에 파일을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="daa75-123">Select and download the .txt file from the setup wizard, then upload the file to your website's top level folder.</span></span> <span data-ttu-id="daa75-124">파일의 경로는 다음과 `http://mydomain.com/ms39978200.txt` 같습니다.</span><span class="sxs-lookup"><span data-stu-id="daa75-124">The path to the file should look similar to: `http://mydomain.com/ms39978200.txt`.</span></span> <span data-ttu-id="daa75-125">웹 사이트에서 파일을 찾아 도메인을 소유하고 있는 것을 확인할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="daa75-125">We'll confirm you own the domain by finding the file on your website.</span></span>
    
6. <span data-ttu-id="daa75-126">Microsoft에서 도메인을 사용하는 데 필요한 DNS를 변경하는 방법을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="daa75-126">Choose how you want to make the DNS changes required for Microsoft to use your domain.</span></span>
    
    1. <span data-ttu-id="daa75-127">등록 **기관에서** [Domain Connect를](#domain-connect-registrars-integrating-with-microsoft-365)지원하고 [Microsoft에서](../get-help-with-domains/domain-connect.md) 등록 기관에 로그인하고 Microsoft 365에 대한 연결을 확인하여 자동으로 레코드를 설정하는 경우 DNS 레코드 추가를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="daa75-127">Choose **Add the DNS records for me** if your registrar supports [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span>
    2. <span data-ttu-id="daa75-128">도메인에 특정 Microsoft 365 서비스만 연결하려는 경우 또는 지금 건너뛰고 나중에 이 작업을 진행하려면 **DNS** 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="daa75-128">Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="daa75-129">**무엇을 할지 정확히 아는 경우에만 이 옵션을 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="daa75-129">**Choose this option if you know exactly what you're doing.**</span></span>

7. <span data-ttu-id="daa75-130">*DNS* 레코드를 직접 추가하기로  선택한 경우 다음을 선택하면 도메인을 설정하기 위해 등록 기관 웹 사이트에 추가해야 하는 모든 레코드가 있는 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="daa75-130">If you chose to *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 

    <span data-ttu-id="daa75-131">포털에서 등록 기관을 인식하지 못하는 경우에는 [이러한 일반 지침을 따르면](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) 됩니다.</span><span class="sxs-lookup"><span data-stu-id="daa75-131">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="daa75-132">호스트를 찾으려면 [호스트 별 지침](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) 목록을 확인하고 다음 단계에 따라 필요한 모든 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="daa75-132">Check our list of [host-specific instructions](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="daa75-133">사용 중인 도메인의 DNS 호스팅 공급자 또는 도메인 등록 기관을 모르는 경우 [도메인 등록자 또는 DNS 호스팅 공급자 찾기](../get-help-with-domains/find-your-domain-registrar.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="daa75-133">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="daa75-134">나중에 기다리려면 모든 서비스를 선택하지 않고 계속을 클릭하거나 **이전** 도메인 연결 단계에서 다른  옵션을 선택하고 지금 **건너뛰기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="daa75-134">If you want to wait for later, either unselect all the services and click **Continue**, or in the previous domain connection step choose **More Options** and select **Skip this for now**.</span></span>
    
8. <span data-ttu-id="daa75-135">Select **Finish** - you're done!</span><span class="sxs-lookup"><span data-stu-id="daa75-135">Select **Finish** - you're done!</span></span>

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="daa75-136">사용자 지정 DNS 레코드 추가 또는 편집</span><span class="sxs-lookup"><span data-stu-id="daa75-136">Add or edit custom DNS records</span></span>

<span data-ttu-id="daa75-137">아래 단계에 따라 웹 사이트 또는 제3자 서비스에 대한 사용자 지정 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="daa75-137">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="daa75-138">.에서 Microsoft 관리 센터에 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="daa75-138">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="daa75-139">설정 도메인    >  **페이지로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="daa75-139">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="daa75-140">**도메인** 페이지에서 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="daa75-140">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="daa75-141">**DNS 설정에서** 사용자 지정 **레코드를 선택합니다.** 그런 다음 **새 사용자 지정 레코드를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="daa75-141">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="daa75-142">추가할 DNS 레코드 유형을 선택하고 새 레코드에 대한 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="daa75-142">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="daa75-143">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="daa75-143">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="daa75-144">도메인 연결을 사용하여 등록자</span><span class="sxs-lookup"><span data-stu-id="daa75-144">Registrars with Domain Connect</span></span>

<span data-ttu-id="daa75-145">[도메인 연결](https://www.domainconnect.org/) 사용 등록 기관을 사용하면 몇 분 정도 걸리는 3단계 프로세스에서 도메인을 Microsoft 365에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daa75-145">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="daa75-146">마법사에서 도메인을 소유하고 있는 것을 확인한 다음 도메인의 레코드를 자동으로 설정하게 되며, 전자 메일이 Microsoft 365 및 Teams와 같은 기타 Microsoft 365 서비스로 전송되면 도메인과 함께 작업합니다.</span><span class="sxs-lookup"><span data-stu-id="daa75-146">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="daa75-147">설정 마법사를 시작하기 전에 브라우저의 팝업 차단 기능을 해제하세요.</span><span class="sxs-lookup"><span data-stu-id="daa75-147">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="daa75-148">Microsoft 365와 통합하는 도메인 연결 등록자</span><span class="sxs-lookup"><span data-stu-id="daa75-148">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="daa75-149">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="daa75-149">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="daa75-150">EuroDNS</span><span class="sxs-lookup"><span data-stu-id="daa75-150">EuroDNS</span></span>](https://www.eurodns.com/)
- [<span data-ttu-id="daa75-151">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="daa75-151">Cloudflare</span></span>](https://www.cloudflare.com/)
- [<span data-ttu-id="daa75-152">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="daa75-152">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="daa75-153">WordPress.com</span><span class="sxs-lookup"><span data-stu-id="daa75-153">WordPress.com</span></span>](https://wordpress.com/)
- [<span data-ttu-id="daa75-154">Plesk</span><span class="sxs-lookup"><span data-stu-id="daa75-154">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="daa75-155">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="daa75-155">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="daa75-156">SecureServer 또는 WildWestDomains(SecureServer DNS 호스팅을 사용하는 GoDaddy 리셀러)</span><span class="sxs-lookup"><span data-stu-id="daa75-156">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - <span data-ttu-id="daa75-157">예제:</span><span class="sxs-lookup"><span data-stu-id="daa75-157">Examples:</span></span>
        - [<span data-ttu-id="daa75-158">DomainsPricedRight</span><span class="sxs-lookup"><span data-stu-id="daa75-158">DomainsPricedRight</span></span>](https://www.domainspricedright.com/products/domain-registration)
        - [<span data-ttu-id="daa75-159">DomainRightNow</span><span class="sxs-lookup"><span data-stu-id="daa75-159">DomainRightNow</span></span>](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="daa75-160">전자 메일 및 웹 사이트는 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="daa75-160">What happens to my email and website?</span></span>

<span data-ttu-id="daa75-161">설치를 마친 후 도메인의 MX 레코드가 Microsoft 365를 지점으로 업데이트하고 도메인의 모든 전자 메일이 Microsoft 365로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="daa75-161">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="daa75-162">도메인에서 전자 메일을 받는 모든 사용자에 대해 Microsoft 365에서 사용자를 추가하고 사서함을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="daa75-162">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="daa75-163">업무에 사용하는 웹 사이트가 있는 경우 어디에 있든 작동이 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="daa75-163">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="daa75-164">도메인 연결 설정 단계는 웹 사이트에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="daa75-164">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="daa75-165">관련 문서</span><span class="sxs-lookup"><span data-stu-id="daa75-165">Related articles</span></span>

[<span data-ttu-id="daa75-166">도메인 FAQ</span><span class="sxs-lookup"><span data-stu-id="daa75-166">Domains FAQ</span></span>](domains-faq.yml)

[<span data-ttu-id="daa75-167">도메인이 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="daa75-167">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="daa75-168">Microsoft 365에서 도메인 이름 구입하기</span><span class="sxs-lookup"><span data-stu-id="daa75-168">Buy a domain name in Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="daa75-169">도메인 설정(호스트별 지침)</span><span class="sxs-lookup"><span data-stu-id="daa75-169">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)
