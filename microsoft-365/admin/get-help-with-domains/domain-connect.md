---
title: 도메인 커넥트
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: 도메인 등록 기관에서 작업하고 커넥트 등록 기관에 도메인을 추가하는 Microsoft 365.
ms.openlocfilehash: 12e1f227c0a157414b56fd04f99e5460a1eb05d4
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228016"
---
# <a name="using-domain-connect"></a><span data-ttu-id="3bc26-103">도메인 커넥트</span><span class="sxs-lookup"><span data-stu-id="3bc26-103">Using Domain Connect</span></span>

 <span data-ttu-id="3bc26-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="3bc26-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="3bc26-105">[도메인 커넥트](https://www.domainconnect.org/) 등록 기관을 사용하면 몇 분 정도 Microsoft 365 3단계 프로세스에서 도메인을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bc26-105">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span>

<span data-ttu-id="3bc26-106">마법사에서 사용자가 도메인을 소유하고 있는 것을 확인한 다음 도메인의 레코드를 자동으로 설정하기만 하여 전자 메일이 도메인과 Microsoft 365 Microsoft 365 서비스와 Teams 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bc26-106">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>

> [!NOTE]
> <span data-ttu-id="3bc26-107">설정 마법사를 시작하기 전에 브라우저의 팝업 차단 기능을 해제하세요.</span><span class="sxs-lookup"><span data-stu-id="3bc26-107">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>

## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="3bc26-108">도메인 커넥트 통합하는 도메인 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3bc26-108">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="3bc26-109">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="3bc26-109">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="3bc26-110">123Reg</span><span class="sxs-lookup"><span data-stu-id="3bc26-110">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="3bc26-111">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="3bc26-111">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="3bc26-112">WordPress</span><span class="sxs-lookup"><span data-stu-id="3bc26-112">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="3bc26-113">Plesk</span><span class="sxs-lookup"><span data-stu-id="3bc26-113">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="3bc26-114">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="3bc26-114">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="3bc26-115">SecureServer 또는 WildWestDomains(SecureServer DNS 호스팅을 사용하는 GoDaddy 리셀러)</span><span class="sxs-lookup"><span data-stu-id="3bc26-115">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
  - [<span data-ttu-id="3bc26-116">MadDog 웹 호스팅</span><span class="sxs-lookup"><span data-stu-id="3bc26-116">MadDog Web Hosting</span></span>](https://maddogwebhosting.com/domains/)
  - [<span data-ttu-id="3bc26-117">CheapNames</span><span class="sxs-lookup"><span data-stu-id="3bc26-117">CheapNames</span></span>](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="3bc26-118">전자 메일 및 웹 사이트는 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="3bc26-118">What happens to my email and website?</span></span>

<span data-ttu-id="3bc26-119">설정이 완료되면 도메인의 MX 레코드가 도메인을 Microsoft 365 도메인의 모든 전자 메일이 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3bc26-119">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="3bc26-120">도메인에서 전자 메일을 받는 모든 Microsoft 365 사용자를 추가하고 사서함을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bc26-120">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>

<span data-ttu-id="3bc26-121">업무에 사용하는 웹 사이트가 있는 경우 어디에 있든 작동이 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bc26-121">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="3bc26-122">Domain 커넥트 설정 단계는 웹 사이트에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3bc26-122">The Domain Connect setup steps don't affect your website.</span></span>
