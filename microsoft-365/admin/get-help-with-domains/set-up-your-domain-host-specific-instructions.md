---
title: 도메인 설정(호스트별 지침)
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
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: ae950c9e-e8d9-4108-b0cb-449156998580
description: 자체 DNS 레코드를 관리하거나 Microsoft에서 DNS 레코드를 관리하게 하는 방법을 배워야 합니다.
ms.openlocfilehash: f3c3710320c62d20c6a16818cd138c9b686d2781
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915569"
---
# <a name="set-up-your-domain-host-specific-instructions"></a><span data-ttu-id="77257-103">도메인 설정(호스트별 지침)</span><span class="sxs-lookup"><span data-stu-id="77257-103">Set up your domain (host-specific instructions)</span></span>

<span data-ttu-id="77257-104">Microsoft 365에서 사용자 지정 도메인(contoso.com)을 사용하려면 도메인을 확인하고 도메인의 DNS 레코드를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77257-104">To start using a custom domain (contoso.com) with Microsoft 365, you need to verify your domain and configure your domain's DNS records.</span></span> 
  
<span data-ttu-id="77257-105">도메인 호스트의 관리 도구를 사용하여 DNS 레코드를 추가 및 관리하거나 Microsoft에 도메인 레코드에 대한 제어를 제공하면 해당 레코드가 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="77257-105">You can add and manage DNS records using the administrative tools at your domain host, or give Microsoft control of your domain records and we'll set them up for you.</span></span>
  
<span data-ttu-id="77257-106">정확한 단계는 아래에서 도메인 호스트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77257-106">Select your domain host below for the exact steps.</span></span> <span data-ttu-id="77257-107">호스트가 누구에게 있는지 확실하지 않은 경우 도메인 등록 기관 [찾기를 참조합니다.](find-your-domain-registrar.md)</span><span class="sxs-lookup"><span data-stu-id="77257-107">If you're not sure who your host is, see [Find your domain registrar](find-your-domain-registrar.md).</span></span>
  

## <a name="let-microsoft-365-manage-your-dns-records"></a><span data-ttu-id="77257-108">Microsoft 365에서 DNS 레코드 관리</span><span class="sxs-lookup"><span data-stu-id="77257-108">Let Microsoft 365 manage your DNS records</span></span>

||
|---|---|
|[<span data-ttu-id="77257-109">1&1 IONOS</span><span class="sxs-lookup"><span data-stu-id="77257-109">1&1 IONOS</span></span>](../dns/change-nameservers-at-1-1-internet.md) |
|[<span data-ttu-id="77257-110">AWS(Amazon Web Services)</span><span class="sxs-lookup"><span data-stu-id="77257-110">Amazon Web Services (AWS)</span></span>](../dns/change-nameservers-at-aws.md) |
 [<span data-ttu-id="77257-111">Bluehost</span><span class="sxs-lookup"><span data-stu-id="77257-111">Bluehost</span></span>](../dns/change-nameservers-at-bluehost.md)|
|[<span data-ttu-id="77257-112">Google Domains</span><span class="sxs-lookup"><span data-stu-id="77257-112">Google   Domains</span></span>](../dns/change-nameservers-at-google-domains.md) |
|[<span data-ttu-id="77257-113">Hostgator   </span><span class="sxs-lookup"><span data-stu-id="77257-113">Hostgator   </span></span>](../dns/change-nameservers-at-hostgator.md)  |  
|[<span data-ttu-id="77257-114">MyDomain</span><span class="sxs-lookup"><span data-stu-id="77257-114">MyDomain</span></span>](../dns/change-nameservers-at-mydomain.md) | 
|[<span data-ttu-id="77257-115">Namecheap</span><span class="sxs-lookup"><span data-stu-id="77257-115">Namecheap</span></span>](../dns/change-nameservers-at-namecheap.md)|
|[<span data-ttu-id="77257-116">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="77257-116">Network Solutions</span></span>](../dns/change-nameservers-at-network-solutions.md) |  

<span data-ttu-id="77257-117">또는 도메인 등록 기관에서 이름 서퍼를 변경하여 [Microsoft 365를 설정하는 방법을 배워야 합니다.](change-nameservers-at-any-domain-registrar.md)</span><span class="sxs-lookup"><span data-stu-id="77257-117">Or, learn how to [change nameservers to set up Microsoft 365 with any domain registrar](change-nameservers-at-any-domain-registrar.md).</span></span>

## <a name="manage-your-own-dns-records"></a><span data-ttu-id="77257-118">자체 DNS 레코드 관리</span><span class="sxs-lookup"><span data-stu-id="77257-118">Manage your own DNS records</span></span>

|                           |                          |
|---------------------------|--------------------------|
| [<span data-ttu-id="77257-119">1&1 IONOS</span><span class="sxs-lookup"><span data-stu-id="77257-119">1&1 IONOS</span></span>](../dns/create-dns-records-at-1-1-internet.md) | [<span data-ttu-id="77257-120">호버</span><span class="sxs-lookup"><span data-stu-id="77257-120">Hover</span></span>](./create-dns-records-at-any-dns-hosting-provider.md) |
| [<span data-ttu-id="77257-121">123-reg.co.uk</span><span class="sxs-lookup"><span data-stu-id="77257-121">123-reg.co.uk</span></span>](../dns/create-dns-records-at-123-reg-co-uk.md) | [<span data-ttu-id="77257-122">Google에서 관리(eNom)</span><span class="sxs-lookup"><span data-stu-id="77257-122">Managed   by Google (eNom)</span></span>](../dns/create-dns-records-for-domain-managed-by-google-enom.md)|
| [<span data-ttu-id="77257-123">AWS(Amazon Web Services)</span><span class="sxs-lookup"><span data-stu-id="77257-123">Amazon Web Services (AWS)</span></span>](../dns/create-dns-records-at-aws.md) | [<span data-ttu-id="77257-124">MyDomain</span><span class="sxs-lookup"><span data-stu-id="77257-124">MyDomain</span></span>](../dns/create-dns-records-at-mydomain.md) |
| [<span data-ttu-id="77257-125">Azure DNS 영역</span><span class="sxs-lookup"><span data-stu-id="77257-125">Azure DNS zones</span></span>](../dns/create-dns-records-for-azure-dns-zones.md) | [<span data-ttu-id="77257-126">name.com</span><span class="sxs-lookup"><span data-stu-id="77257-126">name.com</span></span>](../dns/create-dns-records-at-name-com.md) |
| [<span data-ttu-id="77257-127">Bluehost</span><span class="sxs-lookup"><span data-stu-id="77257-127">Bluehost</span></span>](../dns/create-dns-records-at-bluehost.md) | [<span data-ttu-id="77257-128">Namecheap</span><span class="sxs-lookup"><span data-stu-id="77257-128">Namecheap</span></span>](../dns/create-dns-records-at-namecheap.md)|
| [<span data-ttu-id="77257-129">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="77257-129">Cloudflare</span></span>](../dns/create-dns-records-at-cloudflare.md)| [<span data-ttu-id="77257-130">Names.co.uk</span><span class="sxs-lookup"><span data-stu-id="77257-130">Names.co.uk</span></span>](../dns/create-dns-records-at-names-co-uk.md) |
|  [<span data-ttu-id="77257-131">Crazy Domains</span><span class="sxs-lookup"><span data-stu-id="77257-131">Crazy Domains</span></span>](../dns/create-dns-records-at-crazy-domains.md)| [<span data-ttu-id="77257-132">Netregistry</span><span class="sxs-lookup"><span data-stu-id="77257-132">Netregistry</span></span>](../dns/create-dns-records-at-netregistry.md) |
|[<span data-ttu-id="77257-133">DNSMadeEasy</span><span class="sxs-lookup"><span data-stu-id="77257-133">DNSMadeEasy</span></span>](../dns/create-dns-records-at-dnsmadeeasy.md) | [<span data-ttu-id="77257-134">네트워크 솔루션</span><span class="sxs-lookup"><span data-stu-id="77257-134">Network   Solutions</span></span>](../dns/create-dns-records-at-network-solutions.md) |
|[<span data-ttu-id="77257-135">에코스트</span><span class="sxs-lookup"><span data-stu-id="77257-135">Dreamhost</span></span>](../dns/create-dns-records-at-dreamhost.md)  | [<span data-ttu-id="77257-136">OVH</span><span class="sxs-lookup"><span data-stu-id="77257-136">OVH</span></span>](../dns/create-dns-records-at-ovh.md) |
|  [<span data-ttu-id="77257-137">Dyn.com</span><span class="sxs-lookup"><span data-stu-id="77257-137">Dyn.com</span></span>](../dns/create-dns-records-at-dyn-com.md) | [<span data-ttu-id="77257-138">Register.com</span><span class="sxs-lookup"><span data-stu-id="77257-138">Register.com</span></span>](../dns/create-dns-records-at-register-com.md) |
| [<span data-ttu-id="77257-139">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="77257-139">eNomCentral</span></span>](../dns/create-dns-records-at-enomcentral.md)| [<span data-ttu-id="77257-140">Microsoft 365용 Register365</span><span class="sxs-lookup"><span data-stu-id="77257-140">Register365 for Microsoft 365</span></span>](../dns/create-dns-records-at-register365.md)  |
| [<span data-ttu-id="77257-141">Freenom</span><span class="sxs-lookup"><span data-stu-id="77257-141">Freenom</span></span>](../dns/create-dns-records-at-freenom.md) | [<span data-ttu-id="77257-142"> web.com </span><span class="sxs-lookup"><span data-stu-id="77257-142"> web.com </span></span>](../dns/create-dns-records-at-web-com.md)|
|[<span data-ttu-id="77257-143">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="77257-143">GoDaddy</span></span>](../dns/create-dns-records-at-godaddy.md)|[<span data-ttu-id="77257-144"> Windows 기반 DNS</span><span class="sxs-lookup"><span data-stu-id="77257-144"> Windows-based DNS</span></span>](../dns/create-dns-records-using-windows-based-dns.md)   |
| [<span data-ttu-id="77257-145">Google 도메인</span><span class="sxs-lookup"><span data-stu-id="77257-145">Google Domains</span></span>](../dns/create-dns-records-at-google-domains.md) |[<span data-ttu-id="77257-146">Wix</span><span class="sxs-lookup"><span data-stu-id="77257-146">Wix</span></span>](../dns/create-dns-records-at-wix.md) |
|[<span data-ttu-id="77257-147">Hostgator</span><span class="sxs-lookup"><span data-stu-id="77257-147">Hostgator</span></span>](../dns/create-dns-records-at-hostgator.md)  | [<span data-ttu-id="77257-148">Yahoo!   Small Business</span><span class="sxs-lookup"><span data-stu-id="77257-148">Yahoo!   Small Business</span></span>](../dns/create-dns-records-at-yahoo-small-business.md)  |

[<span data-ttu-id="77257-149">도메인 호스트가 이 목록에 없는 경우 일반 지침이 필요합니다. </span><span class="sxs-lookup"><span data-stu-id="77257-149">I need general instructions, because my domain host isn't on this list. </span></span>](create-dns-records-at-any-dns-hosting-provider.md)
