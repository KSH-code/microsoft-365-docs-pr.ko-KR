---
title: 사용자 지정 도메인을 사용하도록 전자 메일 주소 변경
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: '초기 전자 메일 주소를 전자 메일 주소와 같은 친숙한 전자 메일 주소로 tom@fourthcoffee.com. 이렇게하려면 도메인 이름을 구입하여 Microsoft 365에 추가해야 합니다. '
ms.openlocfilehash: 445b78f759cee79a794f9656afd5b26051534e26
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114024"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a><span data-ttu-id="3e929-104">사용자 지정 도메인을 사용하도록 전자 메일 주소 변경</span><span class="sxs-lookup"><span data-stu-id="3e929-104">Change your email address to use your custom domain</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="3e929-105">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e929-105">The admin center is changing.</span></span> <span data-ttu-id="3e929-106">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3e929-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

 <span data-ttu-id="3e929-107">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="3e929-107">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
::: moniker range="o365-worldwide"

<span data-ttu-id="3e929-108">Microsoft 365의 초기 전자 메일 주소에는 .onmicrosoft.com 포함됩니다(tom@fourthcoffee.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="3e929-108">Your initial email address in Microsoft 365 includes .onmicrosoft.com, like tom@fourthcoffee.onmicrosoft.com.</span></span> <span data-ttu-id="3e929-109">이는 tom@fourthcoffee.com과 같이 보다 친숙한 주소로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e929-109">You can change it to a friendlier address like tom@fourthcoffee.com.</span></span> <span data-ttu-id="3e929-110">먼저 fourthcoffee.com과 같은 고유한 도메인 이름이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3e929-110">You'll need your own domain name, like fourthcoffee.com first.</span></span> <span data-ttu-id="3e929-111">도메인 이름이 이미 있는 경우 해당 도메인을 사용해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e929-111">If you already have one, great!</span></span> <span data-ttu-id="3e929-112">그렇지 않은 경우 [도메인 등록 기관에서 도메인을 구입](../get-help-with-domains/buy-a-domain-name.md)하는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="3e929-112">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="3e929-113">Office 365 Germany의 초기 전자 메일 주소에는 .onmicrosoft.de 포함됩니다(tom@fourthcoffee.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="3e929-113">Your initial email address in Office 365 Germany includes .onmicrosoft.de, like tom@fourthcoffee.onmicrosoft.de.</span></span> <span data-ttu-id="3e929-114">You can change it to a friendlier address like tom@fourthcoffee.de.</span><span class="sxs-lookup"><span data-stu-id="3e929-114">You can change it to a friendlier address like tom@fourthcoffee.de.</span></span> <span data-ttu-id="3e929-115">먼저 도메인 이름과 같은 자체 도메인 fourthcoffee.de 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e929-115">You'll need your own domain name, like fourthcoffee.de first.</span></span> <span data-ttu-id="3e929-116">도메인 이름이 이미 있는 경우 해당 도메인을 사용해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e929-116">If you already have one, great!</span></span> <span data-ttu-id="3e929-117">그렇지 않은 경우 [도메인 등록 기관에서 도메인을 구입](../get-help-with-domains/buy-a-domain-name.md)하는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="3e929-117">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="3e929-118">21Vianet에서 운영하는 Office 365의 초기 전자 메일 주소에는 partner.onmschina.cn 같은 tom@fourthcoffee.partner.onmschina.cn.</span><span class="sxs-lookup"><span data-stu-id="3e929-118">Your initial email address in Office 365 operated by 21Vianet includes partner.onmschina.cn, like tom@fourthcoffee.partner.onmschina.cn.</span></span> <span data-ttu-id="3e929-119">You can change it to a friendlier address like tom@fourthcoffee.cn.</span><span class="sxs-lookup"><span data-stu-id="3e929-119">You can change it to a friendlier address like tom@fourthcoffee.cn.</span></span> <span data-ttu-id="3e929-120">먼저 도메인 이름과 같은 자체 도메인 fourthcoffee.cn 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e929-120">You'll need your own domain name, like fourthcoffee.cn first.</span></span> <span data-ttu-id="3e929-121">도메인 이름이 이미 있는 경우 해당 도메인을 사용해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e929-121">If you already have one, great!</span></span> <span data-ttu-id="3e929-122">그렇지 않은 경우 [도메인 등록 기관에서 도메인을 구입](../get-help-with-domains/buy-a-domain-name.md)하는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="3e929-122">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

<span data-ttu-id="3e929-123">When you change your domain's email to come to Microsoft 365, by updating your domain's MX record during setup, all email sent to that domain will start coming to Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3e929-123">When you change your domain's email to come to Microsoft 365, by updating your domain's MX record during setup, ALL email sent to that domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="3e929-124">MX 레코드를 변경하기 전에 도메인에 전자 메일이 있는 모든 사용자에 대해 Microsoft 365에서 사용자를 추가하고 사서함을 만들었다고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e929-124">Make sure you've added users and created mailboxes in Microsoft 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span> <span data-ttu-id="3e929-125">도메인의 모든 사용자에 대한 전자 메일을 Microsoft 365로 이동하고 싶지 않은가요?</span><span class="sxs-lookup"><span data-stu-id="3e929-125">Don't want to move email for everyone on your domain to Microsoft 365?</span></span> <span data-ttu-id="3e929-126">대신 몇 가지 전자 메일 주소만 사용하여 [Microsoft 365를](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain?view=o365-worldwide)시험해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e929-126">You can take steps to [pilot Microsoft 365 with just a few email addresses instead](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain?view=o365-worldwide).</span></span>
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a><span data-ttu-id="3e929-127">Microsoft 365 관리 센터를 사용하여 사용자 지정 도메인을 사용하기 위해 전자 메일 주소 변경</span><span class="sxs-lookup"><span data-stu-id="3e929-127">Change your email address to use your custom domain using the Microsoft 365 admin center</span></span>

<span data-ttu-id="3e929-128">이러한 단계를 수행하려면 전역 관리자 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e929-128">You must have a global admin account to perform these steps.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3e929-129"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3e929-129">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. <span data-ttu-id="3e929-130"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3e929-130">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span> 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3e929-131">의 관리 센터로 이동하세요. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a></span><span class="sxs-lookup"><span data-stu-id="3e929-131">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn</a>.</span></span> 

::: moniker-end 

2. <span data-ttu-id="3e929-132">설치 도메인   >  **페이지로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3e929-132">Go to the **Setup** > **Domains** page.</span></span> 

3. <span data-ttu-id="3e929-133">**도메인** 페이지에서 **도메인 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3e929-133">On the **Domains** page, select **Add domain**.</span></span>
    
4. <span data-ttu-id="3e929-134">단계를 따라 도메인 소유 여부를 확인하고 전자 메일 주소를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3e929-134">Follow the steps to confirm that you own your domain and to change your email address.</span></span>
    
<span data-ttu-id="3e929-135">Microsoft 365에서 도메인을 올바르게 설정하는 모든 것이 안내됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e929-135">You'll be guided to get everything set up correctly with your domain in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="3e929-136">Exchange 라이선스를 사용하지 않는 경우 해당 도메인을 사용하여 Microsoft 365 테넌트에서 전자 메일을 보내거나 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e929-136">If you are not using an Exchange license, you cannot use the domain to send or receive emails from the Microsoft 365 tenant.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="3e929-137">관련 문서</span><span class="sxs-lookup"><span data-stu-id="3e929-137">Related articles</span></span>

[<span data-ttu-id="3e929-138">Microsoft 365를 사용하여 사용자 지정 도메인 구입</span><span class="sxs-lookup"><span data-stu-id="3e929-138">Buy a custom domain using Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)
 
