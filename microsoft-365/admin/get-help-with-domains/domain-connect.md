---
title: 도메인 연결 사용
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
description: 도메인 연결 사용 등록 기관을 사용 하 여 작업 하 고 도메인을 Microsoft 365에 추가 하는 방법을 알아봅니다.
ms.openlocfilehash: e907317ec5b606c2fe73232a73c9abdfce26feea
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645350"
---
# <a name="using-domain-connect"></a><span data-ttu-id="4f7a0-103">도메인 연결 사용</span><span class="sxs-lookup"><span data-stu-id="4f7a0-103">Using Domain Connect</span></span>

 <span data-ttu-id="4f7a0-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="4f7a0-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="4f7a0-105">[도메인 연결 ](https://www.domainconnect.org/) 사용 등록 기관는 3 단계 프로세스에서 분 단위로 Microsoft 365에 도메인을 추가할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7a0-105">[Domain Connect ](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="4f7a0-106">이 마법사에서는 도메인을 소유 하 고 있는지 확인 하 고, 사용자의 도메인 레코드를 자동으로 설정 하 여 전자 메일이 Microsoft 365 및 기타 Microsoft 365 서비스 (예를 들어, 사용자의 도메인으로 작업)를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7a0-106">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4f7a0-107">설정 마법사를 시작하기 전에 브라우저의 팝업 차단 기능을 해제하세요.</span><span class="sxs-lookup"><span data-stu-id="4f7a0-107">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="4f7a0-108">도메인 연결 등록 기관 Microsoft 365 통합</span><span class="sxs-lookup"><span data-stu-id="4f7a0-108">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="4f7a0-109">1 &amp; 1gb 이상 os</span><span class="sxs-lookup"><span data-stu-id="4f7a0-109">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="4f7a0-110">123Reg</span><span class="sxs-lookup"><span data-stu-id="4f7a0-110">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="4f7a0-111">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="4f7a0-111">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="4f7a0-112">WordPress</span><span class="sxs-lookup"><span data-stu-id="4f7a0-112">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="4f7a0-113">Plesk</span><span class="sxs-lookup"><span data-stu-id="4f7a0-113">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="4f7a0-114">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="4f7a0-114">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="4f7a0-115">SecureServer 또는 WildWestDomains (SecureServer DNS 호스팅을 사용 하는 GoDaddy 리셀러)</span><span class="sxs-lookup"><span data-stu-id="4f7a0-115">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="4f7a0-116">MadDog 도메인</span><span class="sxs-lookup"><span data-stu-id="4f7a0-116">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="4f7a0-117">CheapNames</span><span class="sxs-lookup"><span data-stu-id="4f7a0-117">CheapNames</span></span>](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="4f7a0-118">전자 메일 및 웹 사이트는 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="4f7a0-118">What happens to my email and website?</span></span>

<span data-ttu-id="4f7a0-119">설치를 마친 후에는 도메인에 대 한 MX 레코드가 Microsoft 365를 가리키도록 업데이트 되 고 도메인의 모든 전자 메일이 Microsoft 365로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f7a0-119">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="4f7a0-120">도메인에 전자 메일을 보내는 모든 사용자에 대해 사용자를 추가 하 고 Microsoft 365에 사서함을 설정 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7a0-120">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="4f7a0-121">업무에 사용하는 웹 사이트가 있는 경우 어디에 있든 작동이 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f7a0-121">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="4f7a0-122">도메인 연결 설정 단계는 웹 사이트에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f7a0-122">The Domain Connect setup steps don't affect your website.</span></span>
