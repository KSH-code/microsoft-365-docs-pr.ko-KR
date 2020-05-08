---
title: 사용자 지정 도메인을 사용하도록 전자 메일 주소 변경
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: '초기 전자 메일 주소를 tom@fourthcoffee.com와 같은 친숙 한 전자 메일 주소로 변경 합니다. 이 작업을 수행 하려면 도메인 이름을 구입 하 여 Microsoft 365에 추가 해야 합니다. '
ms.openlocfilehash: 50739c01fda9528140870798324dd69a1c68abce
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140503"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a><span data-ttu-id="98c3b-104">사용자 지정 도메인을 사용하도록 전자 메일 주소 변경</span><span class="sxs-lookup"><span data-stu-id="98c3b-104">Change your email address to use your custom domain</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="98c3b-105">관리 센터가 변경 되는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="98c3b-105">The admin center is changing.</span></span> <span data-ttu-id="98c3b-106">환경이 여기에 나와 있는 세부 정보와 일치 하지 않으면 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98c3b-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

 <span data-ttu-id="98c3b-107">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="98c3b-107">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
::: moniker range="o365-worldwide"

<span data-ttu-id="98c3b-108">Microsoft 365의 초기 전자 메일 주소에는 tom@fourthcoffee.onmicrosoft.com와 같은 onmicrosoft.com이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c3b-108">Your initial email address in Microsoft 365 includes .onmicrosoft.com, like tom@fourthcoffee.onmicrosoft.com.</span></span> <span data-ttu-id="98c3b-109">이는 tom@fourthcoffee.com과 같이 보다 친숙한 주소로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c3b-109">You can change it to a friendlier address like tom@fourthcoffee.com.</span></span> <span data-ttu-id="98c3b-110">먼저 fourthcoffee.com과 같은 고유한 도메인 이름이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="98c3b-110">You'll need your own domain name, like fourthcoffee.com first.</span></span> <span data-ttu-id="98c3b-111">도메인 이름이 이미 있는 경우 해당 도메인을 사용해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c3b-111">If you already have one, great!</span></span> <span data-ttu-id="98c3b-112">그렇지 않은 경우 [도메인 등록 기관에서 도메인을 구입](../get-help-with-domains/buy-a-domain-name.md)하는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="98c3b-112">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="98c3b-113">Office 365 독일의 초기 전자 메일 주소에는 tom@fourthcoffee.onmicrosoft.de와 같은 onmicrosoft.de이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c3b-113">Your initial email address in Office 365 Germany includes .onmicrosoft.de, like tom@fourthcoffee.onmicrosoft.de.</span></span> <span data-ttu-id="98c3b-114">Tom@fourthcoffee.de와 같은 보다 친숙 한 주소로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c3b-114">You can change it to a friendlier address like tom@fourthcoffee.de.</span></span> <span data-ttu-id="98c3b-115">먼저 fourthcoffee.de과 같은 고유한 도메인 이름이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c3b-115">You'll need your own domain name, like fourthcoffee.de first.</span></span> <span data-ttu-id="98c3b-116">도메인 이름이 이미 있는 경우 해당 도메인을 사용해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c3b-116">If you already have one, great!</span></span> <span data-ttu-id="98c3b-117">그렇지 않은 경우 [도메인 등록 기관에서 도메인을 구입](../get-help-with-domains/buy-a-domain-name.md)하는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="98c3b-117">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="98c3b-118">21Vianet에서 운영 하는 Office 365의 초기 전자 메일 주소에는 tom@fourthcoffee.partner.onmschina.cn와 같은 partner.onmschina.cn 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c3b-118">Your initial email address in Office 365 operated by 21Vianet includes partner.onmschina.cn, like tom@fourthcoffee.partner.onmschina.cn.</span></span> <span data-ttu-id="98c3b-119">Tom@fourthcoffee.cn와 같은 보다 친숙 한 주소로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c3b-119">You can change it to a friendlier address like tom@fourthcoffee.cn.</span></span> <span data-ttu-id="98c3b-120">먼저 fourthcoffee.cn과 같은 고유한 도메인 이름이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c3b-120">You'll need your own domain name, like fourthcoffee.cn first.</span></span> <span data-ttu-id="98c3b-121">도메인 이름이 이미 있는 경우 해당 도메인을 사용해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c3b-121">If you already have one, great!</span></span> <span data-ttu-id="98c3b-122">그렇지 않은 경우 [도메인 등록 기관에서 도메인을 구입](../get-help-with-domains/buy-a-domain-name.md)하는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="98c3b-122">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

<span data-ttu-id="98c3b-123">설치 하는 동안 도메인의 MX 레코드를 업데이트 하 여 도메인의 전자 메일을 Microsoft 365로 변경 하면 해당 도메인으로 전송 되는 모든 전자 메일이 Microsoft 365로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c3b-123">When you change your domain's email to come to Microsoft 365, by updating your domain's MX record during setup, ALL email sent to that domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="98c3b-124">MX 레코드를 변경 하기 전에 도메인에 전자 메일이 있는 모든 사용자가 Microsoft 365에서 사용자를 추가 하 고 사서함을 만들었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c3b-124">Make sure you've added users and created mailboxes in Microsoft 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span> <span data-ttu-id="98c3b-125">도메인의 모든 사용자에 대 한 전자 메일을 Microsoft 365로 이동 하지 않으려고 하나요?</span><span class="sxs-lookup"><span data-stu-id="98c3b-125">Don't want to move email for everyone on your domain to Microsoft 365?</span></span> <span data-ttu-id="98c3b-126">[대신 몇 개의 전자 메일 주소만 사용 하 여 Microsoft 365를 파일럿 하는](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)단계를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c3b-126">You can take steps to [pilot Microsoft 365 with just a few email addresses instead](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span></span>
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a><span data-ttu-id="98c3b-127">Microsoft 365 관리 센터를 사용 하 여 사용자 지정 도메인을 사용 하도록 전자 메일 주소 변경</span><span class="sxs-lookup"><span data-stu-id="98c3b-127">Change your email address to use your custom domain using the Microsoft 365 admin center</span></span>

<span data-ttu-id="98c3b-128">이 단계를 수행 하려면 전역 관리자 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c3b-128">You must have a global admin account to perform these steps.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="98c3b-129"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="98c3b-129">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. <span data-ttu-id="98c3b-130"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="98c3b-130">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span> 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="98c3b-131">관리 센터 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>()로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c3b-131">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn</a>.</span></span> 

::: moniker-end 

2. <span data-ttu-id="98c3b-132">**도메인** **설정** > 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c3b-132">Go to the **Setup** > **Domains** page.</span></span> 

3. <span data-ttu-id="98c3b-133">**도메인** 페이지에서 **도메인 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c3b-133">On the **Domains** page, select **Add domain**.</span></span>
    
4. <span data-ttu-id="98c3b-134">단계를 따라 도메인 소유 여부를 확인하고 전자 메일 주소를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="98c3b-134">Follow the steps to confirm that you own your domain and to change your email address.</span></span>
    
<span data-ttu-id="98c3b-135">Microsoft 365에서 도메인에 대 한 모든 기능을 올바르게 설정 하는 방법을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c3b-135">You'll be guided to get everything set up correctly with your domain in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="98c3b-136">Exchange 라이선스를 사용 하지 않는 경우에는 도메인을 사용 하 여 Microsoft 365 테 넌 트에서 전자 메일을 보내거나 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98c3b-136">If you are not using an Exchange license, you cannot use the domain to send or receive emails from the Microsoft 365 tenant.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="98c3b-137">관련 문서</span><span class="sxs-lookup"><span data-stu-id="98c3b-137">Related articles</span></span>

[<span data-ttu-id="98c3b-138">Microsoft 365을 사용 하 여 사용자 지정 도메인 구입</span><span class="sxs-lookup"><span data-stu-id="98c3b-138">Buy a custom domain using Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)
 
