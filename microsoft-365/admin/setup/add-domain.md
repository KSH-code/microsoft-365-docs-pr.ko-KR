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
description: DNS 호스트에서 DNS 레코드를 추가하여 Microsoft 365 관리 센터에서 Microsoft 365에 도메인을 추가합니다. 설정 마법사가 프로세스를 안내합니다.
ms.openlocfilehash: 0adf8b4dcd5d7bd31038b74a574f449f32bfb037
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814435"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="0f044-104">Microsoft 365에 도메인 추가</span><span class="sxs-lookup"><span data-stu-id="0f044-104">Add a domain to Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="0f044-105">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f044-105">The admin center is changing.</span></span> <span data-ttu-id="0f044-106">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f044-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

 <span data-ttu-id="0f044-107">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="0f044-107">**[Check the Domains FAQ](domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="0f044-108">*도메인을 추가, 수정 또는 제거하려면 **비즈니스** **또는 엔터프라이즈** 계획의 [전역 관리자입니다.](https://products.office.com/business/office) 이러한 변경 내용은 전체 테넌트, 사용자 *지정된 관리자 또는* *일반* 사용자에 영향을 주지 않습니다.*</span><span class="sxs-lookup"><span data-stu-id="0f044-108">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="0f044-109">이러한 단계에 따라 도메인을 추가하거나 설정하거나 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="0f044-109">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0f044-110"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0f044-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="0f044-111"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0f044-111">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0f044-112"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0f044-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="0f044-113">설정 도메인 **페이지로**  >  **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f044-113">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="0f044-114">도메인 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f044-114">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="0f044-115">추가할 도메인의 이름을 입력한 후 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f044-115">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="0f044-116">도메인을 소유하고 있는지 확인하는 방법을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0f044-116">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="0f044-117">도메인이 GoDaddy 또는 1 1 1에 등록되어 있는 &amp; 경우 **다음 로그인을**  >  **선택하면** [Microsoft에서 레코드를 자동으로 설정합니다.](../get-help-with-domains/domain-connect.md)</span><span class="sxs-lookup"><span data-stu-id="0f044-117">If your domain is registered at GoDaddy or 1&amp;1, select **Sign in** > **Next** and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md).</span></span>
    
    2. <span data-ttu-id="0f044-118">도메인에 대해 등록된 연락처로 확인 코드가 포함된 전자 메일을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f044-118">You can have an email sent to the registered contact for the domain with a verification code.</span></span> <span data-ttu-id="0f044-119">인식되지 않거나 기록된 전자 메일에 액세스할 수 없는 경우 세 번째 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f044-119">If you don't recognize or have access to the email on record, you can use the third option.</span></span>
    
    3. <span data-ttu-id="0f044-120">TXT 레코드를 사용하여 도메인을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f044-120">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="0f044-121">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span><span class="sxs-lookup"><span data-stu-id="0f044-121">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="0f044-122">레코드를 추가한 후 확인하는 데 최대 30분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f044-122">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    
6. <span data-ttu-id="0f044-123">Office에서 도메인을 사용하려면 필요한 DNS 변경 방법을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0f044-123">Choose how you want to make the DNS changes required for Office to use your domain.</span></span>
    
    1. <span data-ttu-id="0f044-124">Office에서 **DNS를 자동으로 구성하도록** 하려면 하려면 내 DNS 레코드 추가를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0f044-124">Choose **Add the DNS records for me** if you want Office to configure your DNS automatically.</span></span> 
    
  
    2. <span data-ttu-id="0f044-125">특정 Microsoft 365 **서비스만 도메인에 연결하거나** 지금은 이 단계를 건너뛰고 나중에 수행하려는 경우 DNS 레코드를 자신에게 추가하세요.</span><span class="sxs-lookup"><span data-stu-id="0f044-125">Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="0f044-126">**무엇을 할지 정확히 아는 경우에만 이 옵션을 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="0f044-126">**Choose this option if you know exactly what you're doing.**</span></span>
    
7. <span data-ttu-id="0f044-127">DNS 레코드를  *자체적으로 추가하도록 선택한*  경우 다음을 선택하면 **다음을** 선택한 다음 도메인을 설정하기 위해 등록 기관 웹 사이트에 추가해야 하는 모든 레코드가 포함된 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f044-127">If you chose to  *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 
    
  
  
    <span data-ttu-id="0f044-128">포털에서 등록 기관을 인식하지 못하는 경우에는 [이러한 일반 지침을 따르면](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f044-128">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="0f044-129">호스트를 찾으려면 [호스트 별 지침](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) 목록을 확인하고 다음 단계에 따라 필요한 모든 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0f044-129">Check our list of [host-specific instructions](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="0f044-130">사용 중인 도메인의 DNS 호스팅 공급자 또는 도메인 등록 기관을 모르는 경우 [도메인 등록자 또는 DNS 호스팅 공급자 찾기](../get-help-with-domains/find-your-domain-registrar.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f044-130">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="0f044-131">나중에 기다리려면 맨 아래로 스크롤하고 이 단계건 **건너뜁니다.**</span><span class="sxs-lookup"><span data-stu-id="0f044-131">If you want to wait for later, scroll to the bottom and select **Skip this step**.</span></span>
    
8. <span data-ttu-id="0f044-132">**마침** - 모두 마침을 선택하면 완료되었습니다!</span><span class="sxs-lookup"><span data-stu-id="0f044-132">Select **Finish** - you're done!</span></span> 

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="0f044-133">사용자 지정 DNS 레코드 추가 또는 편집</span><span class="sxs-lookup"><span data-stu-id="0f044-133">Add or edit custom DNS records</span></span>

<span data-ttu-id="0f044-134">아래 단계에 따라 웹 사이트 또는 타사 서비스에 대한 사용자 지정 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0f044-134">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="0f044-135">Microsoft 관리 센터에 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="0f044-135">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="0f044-136">설정 도메인 **페이지로**   >  **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f044-136">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="0f044-137">**도메인** 페이지에서 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0f044-137">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="0f044-138">**DNS 설정 아래에서**사용자 **지정 레코드 선택** 그런 다음 새 **사용자 지정 레코드를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f044-138">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="0f044-139">추가할 DNS 레코드 유형을 선택하고 새 레코드의 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0f044-139">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="0f044-140">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0f044-140">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="0f044-141">도메인 연결 등록자</span><span class="sxs-lookup"><span data-stu-id="0f044-141">Registrars with Domain Connect</span></span>

<span data-ttu-id="0f044-142">[도메인 연결을](https://www.domainconnect.org/) 활성화한 등록자를 사용하면 3단계를 통해 몇 분만 에온 3단계 프로세스에서 Microsoft 365에 도메인을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f044-142">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="0f044-143">마법사에서 사용자가 도메인을 소유하고 있다는 사후 자동으로 도메인의 레코드를 설정하므로 Microsoft 365 및 기타 Microsoft 365 서비스(예: Teams)가 사용자의 도메인으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="0f044-143">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0f044-144">설정 마법사를 시작하기 전에 브라우저의 팝업 차단 기능을 해제하세요.</span><span class="sxs-lookup"><span data-stu-id="0f044-144">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="0f044-145">Microsoft 365에 도메인 연결 등록 등록 기관 통합</span><span class="sxs-lookup"><span data-stu-id="0f044-145">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="0f044-146">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="0f044-146">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="0f044-147">123Reg</span><span class="sxs-lookup"><span data-stu-id="0f044-147">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="0f044-148">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="0f044-148">Cloudflare</span></span>](https://www.cloudflare.com/)
- [<span data-ttu-id="0f044-149">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="0f044-149">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="0f044-150">WordPress</span><span class="sxs-lookup"><span data-stu-id="0f044-150">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="0f044-151">Plesk</span><span class="sxs-lookup"><span data-stu-id="0f044-151">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="0f044-152">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="0f044-152">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="0f044-153">SecureServer 또는 WildWestDomains(SecureServer DNS 호스팅을 사용하는 GoDaddy 재판매인)</span><span class="sxs-lookup"><span data-stu-id="0f044-153">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="0f044-154">MadDog 도메인</span><span class="sxs-lookup"><span data-stu-id="0f044-154">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="0f044-155">CheapNames</span><span class="sxs-lookup"><span data-stu-id="0f044-155">CheapNames</span></span>](https://www.cheapnames.com)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="0f044-156">내 전자 메일 및 웹 사이트는 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="0f044-156">What happens to my email and website?</span></span>

<span data-ttu-id="0f044-157">설정이 완료되면 도메인의 MX 레코드가 Microsoft 365를 가리키도록 업데이트되고 도메인의 모든 전자 메일이 Microsoft 365로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f044-157">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="0f044-158">해당 도메인에서 전자 메일을 받는 모든 사용자에 대해 Microsoft 365에서 사용자를 추가하고 사서함을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f044-158">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="0f044-159">업무에 사용하는 웹 사이트가 있는 경우 어디에 있든 작동이 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f044-159">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="0f044-160">도메인 연결 설정 단계는 사용자 웹 사이트에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f044-160">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="0f044-161">관련 문서</span><span class="sxs-lookup"><span data-stu-id="0f044-161">Related articles</span></span>

[<span data-ttu-id="0f044-162">도메인 FAQ</span><span class="sxs-lookup"><span data-stu-id="0f044-162">Domains FAQ</span></span>](domains-faq.md)

[<span data-ttu-id="0f044-163">도메인이 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="0f044-163">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="0f044-164">Microsoft 365에서 도메인 이름 구입하기</span><span class="sxs-lookup"><span data-stu-id="0f044-164">Buy a domain name in Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="0f044-165">도메인 설정(호스트별 지침)</span><span class="sxs-lookup"><span data-stu-id="0f044-165">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)
