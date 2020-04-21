---
title: 도메인 설정(호스트별 지침)
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
search.appverid:
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: ae950c9e-e8d9-4108-b0cb-449156998580
description: 자체 DNS 레코드를 관리 하는 방법 또는 Microsoft에서 DNS 레코드를 관리 하도록 하는 방법을 알아봅니다.
ms.custom: okr_smb
ms.openlocfilehash: ea3a62c048706f36cd7b1590851d8b372e0a1677
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628425"
---
# <a name="set-up-your-domain-host-specific-instructions"></a><span data-ttu-id="f68e6-103">도메인 설정(호스트별 지침)</span><span class="sxs-lookup"><span data-stu-id="f68e6-103">Set up your domain (host-specific instructions)</span></span>

<span data-ttu-id="f68e6-104">Office 365에서 사용자 지정 도메인 (contoso.com)을 사용 하기 시작 하려면 도메인을 확인 하 고 도메인의 DNS 레코드를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f68e6-104">To start using a custom domain (contoso.com) with Office 365, you need to verify your domain and configure your domain's DNS records.</span></span> 
  
<span data-ttu-id="f68e6-105">도메인 호스트에서 관리 도구를 사용 하 여 DNS 레코드를 추가 및 관리할 수 있으며, 도메인 레코드에 대 한 제어 권한을 부여 하 고 사용자를 위해이를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f68e6-105">You can add and manage DNS records using the administrative tools at your domain host, or give Microsoft control of your domain records and we'll set them up for you.</span></span>
  
<span data-ttu-id="f68e6-106">정확한 단계를 보려면 아래에서 도메인 호스트를 선택 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f68e6-106">Select your domain host below for the exact steps.</span></span> <span data-ttu-id="f68e6-107">호스트를 잘 모르는 경우 [domain 등록자 찾기를](find-your-domain-registrar.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f68e6-107">If you're not sure who your host is, see [Find your domain registrar](find-your-domain-registrar.md).</span></span>
  

## <a name="let-office-365-manage-your-dns-records"></a><span data-ttu-id="f68e6-108">Office 365에서 DNS 레코드를 관리 하도록 허용</span><span class="sxs-lookup"><span data-stu-id="f68e6-108">Let Office 365 manage your DNS records</span></span>

||
|---|---|
|[<span data-ttu-id="f68e6-109">1&,.</span><span class="sxs-lookup"><span data-stu-id="f68e6-109">1&1 IONOS</span></span>](../dns/change-nameservers-at-1-1-internet.md) |
|[<span data-ttu-id="f68e6-110">AWS(Amazon Web Services)</span><span class="sxs-lookup"><span data-stu-id="f68e6-110">Amazon Web Services (AWS)</span></span>](../dns/change-nameservers-at-aws.md) |
 [<span data-ttu-id="f68e6-111">Bluehost</span><span class="sxs-lookup"><span data-stu-id="f68e6-111">Bluehost</span></span>](../dns/change-nameservers-at-bluehost.md)|
|[<span data-ttu-id="f68e6-112">Google 도메인</span><span class="sxs-lookup"><span data-stu-id="f68e6-112">Google   Domains</span></span>](../dns/change-nameservers-at-google-domains.md) |
|[<span data-ttu-id="f68e6-113">Hostgator</span><span class="sxs-lookup"><span data-stu-id="f68e6-113">Hostgator   </span></span>](../dns/change-nameservers-at-hostgator.md)  |  
|[<span data-ttu-id="f68e6-114">MyDomain</span><span class="sxs-lookup"><span data-stu-id="f68e6-114">MyDomain</span></span>](../dns/change-nameservers-at-mydomain.md) | 
|[<span data-ttu-id="f68e6-115">Namecheap</span><span class="sxs-lookup"><span data-stu-id="f68e6-115">Namecheap</span></span>](../dns/change-nameservers-at-namecheap.md)|
|[<span data-ttu-id="f68e6-116">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="f68e6-116">Network Solutions</span></span>](../dns/change-nameservers-at-network-solutions.md) |  

<span data-ttu-id="f68e6-117">아니면 [도메인 등록 기관에서 이름 서버를 변경 하 여 Office 365을 설정](change-nameservers-at-any-domain-registrar.md)하는 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="f68e6-117">Or, learn how to [change nameservers to set up Office 365 with any domain registrar](change-nameservers-at-any-domain-registrar.md).</span></span>

## <a name="manage-your-own-dns-records"></a><span data-ttu-id="f68e6-118">자체 DNS 레코드 관리</span><span class="sxs-lookup"><span data-stu-id="f68e6-118">Manage your own DNS records</span></span>

|                           |                          |
|---------------------------|--------------------------|
| [<span data-ttu-id="f68e6-119">1&,.</span><span class="sxs-lookup"><span data-stu-id="f68e6-119">1&1 IONOS</span></span>](../dns/create-dns-records-at-1-1-internet.md) | [<span data-ttu-id="f68e6-120">가리키기</span><span class="sxs-lookup"><span data-stu-id="f68e6-120">Hover</span></span>](../dns/create-dns-records-at-hover.md) |
| [<span data-ttu-id="f68e6-121">123-reg.co.uk</span><span class="sxs-lookup"><span data-stu-id="f68e6-121">123-reg.co.uk</span></span>](../dns/create-dns-records-at-123-reg-co-uk.md) | [<span data-ttu-id="f68e6-122">Google (eNom)에서 관리</span><span class="sxs-lookup"><span data-stu-id="f68e6-122">Managed   by Google (eNom)</span></span>](../dns/create-dns-records-for-domain-managed-by-google-enom.md)|
| [<span data-ttu-id="f68e6-123">AWS(Amazon Web Services)</span><span class="sxs-lookup"><span data-stu-id="f68e6-123">Amazon Web Services (AWS)</span></span>](../dns/create-dns-records-at-aws.md) | [<span data-ttu-id="f68e6-124">MyDomain</span><span class="sxs-lookup"><span data-stu-id="f68e6-124">MyDomain</span></span>](../dns/create-dns-records-at-mydomain.md) |
| [<span data-ttu-id="f68e6-125">Azure DNS 영역</span><span class="sxs-lookup"><span data-stu-id="f68e6-125">Azure DNS zones</span></span>](../dns/create-dns-records-for-azure-dns-zones.md) | [<span data-ttu-id="f68e6-126">name.com</span><span class="sxs-lookup"><span data-stu-id="f68e6-126">name.com</span></span>](../dns/create-dns-records-at-name-com.md) |
| [<span data-ttu-id="f68e6-127">Bluehost</span><span class="sxs-lookup"><span data-stu-id="f68e6-127">Bluehost</span></span>](../dns/create-dns-records-at-bluehost.md) | [<span data-ttu-id="f68e6-128">Namecheap</span><span class="sxs-lookup"><span data-stu-id="f68e6-128">Namecheap</span></span>](../dns/create-dns-records-at-namecheap.md)|
| [<span data-ttu-id="f68e6-129">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="f68e6-129">Cloudflare</span></span>](../dns/create-dns-records-at-cloudflare.md)| [<span data-ttu-id="f68e6-130">Names.co.uk</span><span class="sxs-lookup"><span data-stu-id="f68e6-130">Names.co.uk</span></span>](../dns/create-dns-records-at-names-co-uk.md) |
|  [<span data-ttu-id="f68e6-131">Crazy Domains</span><span class="sxs-lookup"><span data-stu-id="f68e6-131">Crazy Domains</span></span>](../dns/create-dns-records-at-crazy-domains.md)| [<span data-ttu-id="f68e6-132">Netregistry</span><span class="sxs-lookup"><span data-stu-id="f68e6-132">Netregistry</span></span>](../dns/create-dns-records-at-netregistry.md) |
|[<span data-ttu-id="f68e6-133">DNSMadeEasy</span><span class="sxs-lookup"><span data-stu-id="f68e6-133">DNSMadeEasy</span></span>](../dns/create-dns-records-at-dnsmadeeasy.md) | [<span data-ttu-id="f68e6-134">네트워크 솔루션</span><span class="sxs-lookup"><span data-stu-id="f68e6-134">Network   Solutions</span></span>](../dns/create-dns-records-at-network-solutions.md) |
|[<span data-ttu-id="f68e6-135">Dreamhost</span><span class="sxs-lookup"><span data-stu-id="f68e6-135">Dreamhost</span></span>](../dns/create-dns-records-at-dreamhost.md)  | [<span data-ttu-id="f68e6-136">OVH</span><span class="sxs-lookup"><span data-stu-id="f68e6-136">OVH</span></span>](../dns/create-dns-records-at-ovh.md) |
|  [<span data-ttu-id="f68e6-137">Dyn.com</span><span class="sxs-lookup"><span data-stu-id="f68e6-137">Dyn.com</span></span>](../dns/create-dns-records-at-dyn-com.md) | [<span data-ttu-id="f68e6-138">Register.com</span><span class="sxs-lookup"><span data-stu-id="f68e6-138">Register.com</span></span>](../dns/create-dns-records-at-register-com.md) |
| [<span data-ttu-id="f68e6-139">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="f68e6-139">eNomCentral</span></span>](../dns/create-dns-records-at-enomcentral.md)| [<span data-ttu-id="f68e6-140">R 365 for Office 365</span><span class="sxs-lookup"><span data-stu-id="f68e6-140">Register365 for Office 365</span></span>](../dns/create-dns-records-at-register365.md)  |
| [<span data-ttu-id="f68e6-141">Freenom</span><span class="sxs-lookup"><span data-stu-id="f68e6-141">Freenom</span></span>](../dns/create-dns-records-at-freenom.md) | [<span data-ttu-id="f68e6-142">web.com</span><span class="sxs-lookup"><span data-stu-id="f68e6-142"> web.com </span></span>](../dns/create-dns-records-at-web-com.md)|
|[<span data-ttu-id="f68e6-143">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="f68e6-143">GoDaddy</span></span>](../dns/create-dns-records-at-godaddy.md)|[<span data-ttu-id="f68e6-144">Windows 기반 DNS</span><span class="sxs-lookup"><span data-stu-id="f68e6-144"> Windows-based DNS</span></span>](../dns/create-dns-records-using-windows-based-dns.md)   |
| [<span data-ttu-id="f68e6-145">Google 도메인</span><span class="sxs-lookup"><span data-stu-id="f68e6-145">Google Domains</span></span>](../dns/create-dns-records-at-google-domains.md) |[<span data-ttu-id="f68e6-146">Wix</span><span class="sxs-lookup"><span data-stu-id="f68e6-146">Wix</span></span>](../dns/create-dns-records-at-wix.md) |
|[<span data-ttu-id="f68e6-147">Hostgator</span><span class="sxs-lookup"><span data-stu-id="f68e6-147">Hostgator</span></span>](../dns/create-dns-records-at-hostgator.md)  | <span data-ttu-id="f68e6-148">[!   소규모 기업](../dns/create-dns-records-at-yahoo-small-business.md)</span><span class="sxs-lookup"><span data-stu-id="f68e6-148">[Yahoo!   Small Business](../dns/create-dns-records-at-yahoo-small-business.md)</span></span>  |

[<span data-ttu-id="f68e6-149">도메인 호스트가이 목록에 없기 때문에 일반 지침이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f68e6-149">I need general instructions, because my domain host isn't on this list. </span></span>](create-dns-records-at-any-dns-hosting-provider.md)
   
