---
title: Office 365에 도메인 추가
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: DNS 호스트에서 DNS 레코드를 추가 하 여 Microsoft 365 관리 센터에서 Office 365에 도메인을 추가 합니다. 설치 마법사가 프로세스를 안내 합니다.
ms.openlocfilehash: a6ef611ec210bbfb2299b6d41edb7d6410d50073
ms.sourcegitcommit: 8edad75338cf74712ca1ab5d6631b9b52ff54410
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2020
ms.locfileid: "43116017"
---
# <a name="add-a-domain-to-office-365"></a><span data-ttu-id="e24af-104">Office 365에 도메인 추가</span><span class="sxs-lookup"><span data-stu-id="e24af-104">Add a domain to Office 365</span></span>

 <span data-ttu-id="e24af-105">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="e24af-105">**[Check the Domains FAQ](domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="e24af-106">*도메인을 추가, 수정 또는 제거 하려면 [비즈니스 또는 기업 계획](https://products.office.com/business/office)의 **전역 관리자** **여야 합니다** . 이러한 변경 내용은 전체 테 넌 트에 영향을 미치며 *사용자 지정 된 관리자* 또는 *일반 사용자* 는 이러한 변경 작업을 수행할 수 없습니다.*</span><span class="sxs-lookup"><span data-stu-id="e24af-106">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="e24af-107">도메인을 추가, 설정 또는 계속 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e24af-107">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e24af-108"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e24af-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="e24af-109"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e24af-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e24af-110"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e24af-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="e24af-111">**도메인** **설정** > 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e24af-111">Go to the **Setup** > **Domains** page.</span></span> 

3. <span data-ttu-id="e24af-112">**도메인 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e24af-112">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="e24af-113">추가 하려는 도메인의 이름을 입력 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e24af-113">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="e24af-114">도메인을 소유 하 고 있는지 확인 하는 방법을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e24af-114">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="e24af-115">도메인이 godaddy 또는 1&amp;1에 등록 되어 있는 경우**다음** **로그인** > 을 선택 하면 Office 365 [에서 자동으로 레코드를 설정](../get-help-with-domains/domain-connect.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e24af-115">If your domain is registered at GoDaddy or 1&amp;1, select **Sign in** > **Next** and Office 365 [will set up your records automatically](../get-help-with-domains/domain-connect.md).</span></span>
    
    2. <span data-ttu-id="e24af-116">도메인에 대해 등록된 연락처로 확인 코드가 포함된 전자 메일을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e24af-116">You can have an email sent to the registered contact for the domain with a verification code.</span></span> <span data-ttu-id="e24af-117">알 수 없거나 기록 된 전자 메일에 대 한 액세스 권한이 있는 경우 세 번째 옵션을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e24af-117">If you don't recognize or have access to the email on record, you can use the third option.</span></span>
    
    3. <span data-ttu-id="e24af-118">TXT 레코드를 사용하여 도메인을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e24af-118">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="e24af-119">이를 선택 하 고 **다음** 을 선택 하 여 등록자의 웹 사이트에이 DNS 레코드를 추가 하는 방법에 대 한 지침을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e24af-119">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="e24af-120">이 작업은 레코드를 추가한 후 확인 하는 데 최대 30 분까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e24af-120">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    
6. <span data-ttu-id="e24af-121">Office에서 도메인을 사용 하는 데 필요한 DNS 변경 작업을 수행 하는 방법을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e24af-121">Choose how you want to make the DNS changes required for Office to use your domain.</span></span>
    
    1. <span data-ttu-id="e24af-122">Office에서 DNS를 자동으로 구성 하도록 하려면 **dns 레코드 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e24af-122">Choose **Add the DNS records for me** if you want Office to configure your DNS automatically.</span></span> 
    
  
    2. <span data-ttu-id="e24af-123">특정 Office 365 서비스만 도메인에 연결 하거나 지금 건너뛰고 나중에이 작업을 수행 하려는 경우에 **는 직접 DNS 레코드를 추가** 합니다 .를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e24af-123">Choose **I'll add the DNS records myself** if you want to attach only specific Office 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="e24af-124">**무엇을 할지 정확히 아는 경우에만 이 옵션을 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="e24af-124">**Choose this option if you know exactly what you're doing.**</span></span>
    
7. <span data-ttu-id="e24af-125">*DNS 레코드를 직접 추가* 하도록 선택한 경우에는 **다음** 을 선택 하 고 도메인을 설정 하기 위해 등록 기관 웹 사이트에 추가 해야 하는 모든 레코드가 포함 된 페이지를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e24af-125">If you chose to  *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 
    
  
  
    <span data-ttu-id="e24af-126">포털에서 등록 기관을 인식하지 못하는 경우에는 [이러한 일반 지침을 따르면](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e24af-126">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="e24af-127">호스트를 찾으려면 [호스트 별 지침](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) 목록을 확인하고 다음 단계에 따라 필요한 모든 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e24af-127">Check our list of [host-specific instructions](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="e24af-128">사용 중인 도메인의 DNS 호스팅 공급자 또는 도메인 등록 기관을 모르는 경우 [도메인 등록자 또는 DNS 호스팅 공급자 찾기](../get-help-with-domains/find-your-domain-registrar.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e24af-128">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="e24af-129">나중에 기다리도록 하려면 맨 아래로 스크롤한 다음 **이 단계 건너뛰기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e24af-129">If you want to wait for later, scroll to the bottom and select **Skip this step**.</span></span>
    
8. <span data-ttu-id="e24af-130">**완료** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e24af-130">Select **Finish** - you're done!</span></span> 

## <a name="related-articles"></a><span data-ttu-id="e24af-131">관련 문서</span><span class="sxs-lookup"><span data-stu-id="e24af-131">Related articles</span></span>

[<span data-ttu-id="e24af-132">도메인 FAQ</span><span class="sxs-lookup"><span data-stu-id="e24af-132">Domains FAQ</span></span>](domains-faq.md)

[<span data-ttu-id="e24af-133">도메인이 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="e24af-133">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="e24af-134">Office 365에서 도메인 이름 구입</span><span class="sxs-lookup"><span data-stu-id="e24af-134">Buy a domain name in Office 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="e24af-135">도메인 설정(호스트별 지침)</span><span class="sxs-lookup"><span data-stu-id="e24af-135">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[<span data-ttu-id="e24af-136">Office 365 도메인에 대 한 도움말 보기</span><span class="sxs-lookup"><span data-stu-id="e24af-136">Get help with Office 365 domains</span></span>](../get-help-with-domains/get-help-with-domains.md)
