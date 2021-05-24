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
description: DNS 호스트에서 DNS 레코드를 추가하여 Microsoft 365 관리 Microsoft 365 추가하려면 설정 마법사를 사용하여 도메인을 추가합니다.
ms.openlocfilehash: 152144737b0ff8cb8b0c27db2a4fc1051fb2a8a7
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635681"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="19645-103">Microsoft 365에 도메인 추가</span><span class="sxs-lookup"><span data-stu-id="19645-103">Add a domain to Microsoft 365</span></span>

 <span data-ttu-id="19645-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](domains-faq.yml)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="19645-104">**[Check the Domains FAQ](domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="19645-105">*도메인을 추가, 수정 또는 제거하려면  **비즈니스** 또는 엔터프라이즈 계획의 전역 관리자 [되어야 합니다.](https://products.office.com/business/office) 이러한 변경 내용은 전체 테넌트,   사용자 지정된 관리자 또는 일반 사용자에게 영향을 미치며 이러한 변경을 할 수 없습니다.*</span><span class="sxs-lookup"><span data-stu-id="19645-105">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 ## <a name="add-a-domain"></a><span data-ttu-id="19645-106">도메인 추가</span><span class="sxs-lookup"><span data-stu-id="19645-106">Add a domain</span></span>

<span data-ttu-id="19645-107">다음 단계에 따라 도메인을 추가, 설정 또는 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="19645-107">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="19645-108"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="19645-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="19645-109"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="19645-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="19645-110"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="19645-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="19645-111">도메인 **설정**  >  **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="19645-111">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="19645-112">**도메인 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19645-112">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="19645-113">추가할 도메인의 이름을 입력하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="19645-113">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="19645-114">도메인을 소유하고 있는지 확인하는 방법을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="19645-114">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="19645-115">도메인 등록 기관에서 [Domain 커넥트](#domain-connect-registrars-integrating-with-microsoft-365)사용하는 경우 Microsoft는 등록 기관에 로그인하고 등록 기관에 대한 연결을 확인하여 레코드를 Microsoft 365. [](../get-help-with-domains/domain-connect.md)</span><span class="sxs-lookup"><span data-stu-id="19645-115">If your domain registrar uses [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span> <span data-ttu-id="19645-116">You'll be returned to the admin center and Microsoft will automatically verify your domain.</span><span class="sxs-lookup"><span data-stu-id="19645-116">You'll be returned to the admin center and Microsoft will then automatically verify your domain.</span></span>
    2. <span data-ttu-id="19645-117">TXT 레코드를 사용하여 도메인을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19645-117">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="19645-118">이 옵션을 선택하고 **다음을** 선택하여 등록 기관의 웹 사이트에 이 DNS 레코드를 추가하는 방법에 대한 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19645-118">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="19645-119">레코드를 추가한 후 확인하는 데 최대 30분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19645-119">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    3. <span data-ttu-id="19645-120">도메인의 웹 사이트에 텍스트 파일을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19645-120">You can add a text file to your domain's website.</span></span> <span data-ttu-id="19645-121">설치 마법사에서 .txt 파일을 선택하고 다운로드한 다음 웹 사이트의 최상위 폴더에 파일을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="19645-121">Select and download the .txt file from the setup wizard, then upload the file to your website's top level folder.</span></span> <span data-ttu-id="19645-122">파일의 경로는 다음과 유사해야 `http://mydomain.com/ms39978200.txt` 합니다.</span><span class="sxs-lookup"><span data-stu-id="19645-122">The path to the file should look similar to: `http://mydomain.com/ms39978200.txt`.</span></span> <span data-ttu-id="19645-123">웹 사이트에서 파일을 찾아 도메인을 소유하고 있는 것을 확인할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="19645-123">We'll confirm you own the domain by finding the file on your website.</span></span>
    
6. <span data-ttu-id="19645-124">Microsoft에서 도메인을 사용하는 데 필요한 DNS를 변경하는 방법을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="19645-124">Choose how you want to make the DNS changes required for Microsoft to use your domain.</span></span>
    
    1. <span data-ttu-id="19645-125">등록 **기관에서** [Domain 커넥트](#domain-connect-registrars-integrating-with-microsoft-365)지원하는 경우 Dns 레코드 추가를 선택하면 [Microsoft에서](../get-help-with-domains/domain-connect.md) 등록 기관에 로그인하고 등록 기관에 대한 연결을 확인하여 자동으로 레코드를 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="19645-125">Choose **Add the DNS records for me** if your registrar supports [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span>
    2. <span data-ttu-id="19645-126">도메인에 특정 Microsoft 365 서비스만 연결하려는 경우 또는 지금 건너뛰고 나중에 이 작업을 하려는 경우 **DNS** 레코드를 추가합니다.를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="19645-126">Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="19645-127">**무엇을 할지 정확히 아는 경우에만 이 옵션을 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="19645-127">**Choose this option if you know exactly what you're doing.**</span></span>

7. <span data-ttu-id="19645-128">*DNS* 레코드를 직접 추가하기로  선택한 경우 다음을 선택하면 도메인을 설정하기 위해 등록 기관 웹 사이트에 추가해야 하는 모든 레코드가 있는 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="19645-128">If you chose to *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 

    <span data-ttu-id="19645-129">포털에서 등록 기관을 인식하지 못하는 경우에는 [이러한 일반 지침을 따르면](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19645-129">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="19645-130">호스트를 찾으려면 [호스트 별 지침](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) 목록을 확인하고 다음 단계에 따라 필요한 모든 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="19645-130">Check our list of [host-specific instructions](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="19645-131">사용 중인 도메인의 DNS 호스팅 공급자 또는 도메인 등록 기관을 모르는 경우 [도메인 등록자 또는 DNS 호스팅 공급자 찾기](../get-help-with-domains/find-your-domain-registrar.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19645-131">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="19645-132">나중에 기다리려면 모든 서비스를 선택하지 않고 계속을 클릭하거나 이전 도메인 연결 단계에서 더  많은 옵션을 선택하고 지금 **건너뛰기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="19645-132">If you want to wait for later, either unselect all the services and click **Continue**, or in the previous domain connection step choose **More Options** and select **Skip this for now**.</span></span>
    
8. <span data-ttu-id="19645-133">완료 **-** 완료를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19645-133">Select **Finish** - you're done!</span></span>

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="19645-134">사용자 지정 DNS 레코드 추가 또는 편집</span><span class="sxs-lookup"><span data-stu-id="19645-134">Add or edit custom DNS records</span></span>

<span data-ttu-id="19645-135">아래 단계에 따라 웹 사이트 또는 제3자 서비스에 대한 사용자 지정 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="19645-135">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="19645-136">에서 Microsoft 관리 센터에 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="19645-136">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="19645-137">도메인 **설정**   >  **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="19645-137">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="19645-138">**도메인** 페이지에서 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19645-138">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="19645-139">**DNS 설정에서** 사용자 지정 **레코드 를 선택합니다.** 그런 다음 새 사용자 **지정 레코드 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="19645-139">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="19645-140">추가할 DNS 레코드 유형을 선택하고 새 레코드에 대한 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="19645-140">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="19645-141">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19645-141">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="19645-142">도메인 등록자가 있는 커넥트</span><span class="sxs-lookup"><span data-stu-id="19645-142">Registrars with Domain Connect</span></span>

<span data-ttu-id="19645-143">[도메인 커넥트](https://www.domainconnect.org/) 등록 기관을 사용하면 몇 분 정도 Microsoft 365 3단계 프로세스에서 도메인을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19645-143">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="19645-144">마법사에서 사용자가 도메인을 소유하고 있는 것을 확인한 다음 도메인의 레코드를 자동으로 설정하기만 하여 전자 메일이 도메인과 Microsoft 365 Microsoft 365 서비스와 Teams 합니다.</span><span class="sxs-lookup"><span data-stu-id="19645-144">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="19645-145">설정 마법사를 시작하기 전에 브라우저의 팝업 차단 기능을 해제하세요.</span><span class="sxs-lookup"><span data-stu-id="19645-145">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="19645-146">도메인 커넥트 통합하는 도메인 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="19645-146">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="19645-147">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="19645-147">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="19645-148">EuroDNS</span><span class="sxs-lookup"><span data-stu-id="19645-148">EuroDNS</span></span>](https://www.eurodns.com/)
- [<span data-ttu-id="19645-149">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="19645-149">Cloudflare</span></span>](https://www.cloudflare.com/)
- [<span data-ttu-id="19645-150">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="19645-150">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="19645-151">WordPress.com</span><span class="sxs-lookup"><span data-stu-id="19645-151">WordPress.com</span></span>](https://wordpress.com/)
- [<span data-ttu-id="19645-152">Plesk</span><span class="sxs-lookup"><span data-stu-id="19645-152">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="19645-153">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="19645-153">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="19645-154">SecureServer 또는 WildWestDomains(SecureServer DNS 호스팅을 사용하는 GoDaddy 리셀러)</span><span class="sxs-lookup"><span data-stu-id="19645-154">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - <span data-ttu-id="19645-155">예제:</span><span class="sxs-lookup"><span data-stu-id="19645-155">Examples:</span></span>
        - [<span data-ttu-id="19645-156">DomainsPricedRight</span><span class="sxs-lookup"><span data-stu-id="19645-156">DomainsPricedRight</span></span>](https://www.domainspricedright.com/products/domain-registration)
        - [<span data-ttu-id="19645-157">DomainRightNow</span><span class="sxs-lookup"><span data-stu-id="19645-157">DomainRightNow</span></span>](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="19645-158">전자 메일 및 웹 사이트는 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="19645-158">What happens to my email and website?</span></span>

<span data-ttu-id="19645-159">설정이 완료되면 도메인의 MX 레코드가 도메인을 Microsoft 365 도메인의 모든 전자 메일이 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="19645-159">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="19645-160">도메인에서 전자 메일을 받는 모든 Microsoft 365 사용자를 추가하고 사서함을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19645-160">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="19645-161">업무에 사용하는 웹 사이트가 있는 경우 어디에 있든 작동이 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="19645-161">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="19645-162">Domain 커넥트 설정 단계는 웹 사이트에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19645-162">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-content"></a><span data-ttu-id="19645-163">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="19645-163">Related content</span></span>

<span data-ttu-id="19645-164">[도메인](domains-faq.yml) FAQ(문서)</span><span class="sxs-lookup"><span data-stu-id="19645-164">[Domains FAQ](domains-faq.yml) (article)</span></span>\
[<span data-ttu-id="19645-165">도메인이 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="19645-165">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md) <span data-ttu-id="19645-166">(기사)</span><span class="sxs-lookup"><span data-stu-id="19645-166">(article)</span></span>\
<span data-ttu-id="19645-167">[Microsoft 365 도메인](../get-help-with-domains/buy-a-domain-name.md) 이름 구입(문서)</span><span class="sxs-lookup"><span data-stu-id="19645-167">[Buy a domain name in Microsoft 365](../get-help-with-domains/buy-a-domain-name.md) (article)</span></span>\
<span data-ttu-id="19645-168">[도메인](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) 설정(문서)</span><span class="sxs-lookup"><span data-stu-id="19645-168">[Set up your domain](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) (article)</span></span>