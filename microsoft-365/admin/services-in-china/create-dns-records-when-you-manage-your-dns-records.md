---
title: DNS 레코드를 관리할 Office 365 DNS 레코드 만들기
f1.keywords:
- CSH
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEA150
ms.assetid: 0669bf14-414d-4f51-8231-6b710ce7980b
ROBOTS: NOINDEX
description: 'DNS 레코드를 관리할 Office 365 21Vianet에서 운영하는 서버에 대한 DNS 레코드를 만드는 방법을 학습합니다. '
monikerRange: o365-21vianet
ms.openlocfilehash: 1eaa2bcc7263eaa12e53131246abd591006b0536
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914357"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a><span data-ttu-id="cd43c-103">DNS 레코드를 관리할 Office 365 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="cd43c-103">Create DNS records for Office 365 when you manage your DNS records</span></span>

<span data-ttu-id="cd43c-104">메일 라우팅에 필요한 MX 레코드를 포함하여 21Vianet에서 운영하는 Office 365 DNS 레코드를 만드는 방법에 대한 자세한 내용은 [Dns](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)호스팅 공급자에서 DNS 레코드 만들기를 Office 365.</span><span class="sxs-lookup"><span data-stu-id="cd43c-104">For detailed instructions about how to create DNS records for Office 365 operated by 21Vianet, including the MX record required for mail routing, see [Create DNS records at any DNS hosting provider for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> 
  
  
<span data-ttu-id="cd43c-105">추가 옵션 및 주의해야 할 몇 가지 사항:</span><span class="sxs-lookup"><span data-stu-id="cd43c-105">More options and some things to be aware of:</span></span>
      
-  <span data-ttu-id="cd43c-106">사용 중인 도메인의 DNS 호스팅 공급자 또는 도메인 등록 기관을 모르는 경우 [도메인 등록자 또는 DNS 호스팅 공급자 찾기](../get-help-with-domains/find-your-domain-registrar.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cd43c-106">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span> <span data-ttu-id="cd43c-107">DNS 레코드의 기능 설명은 [DNS 기본 을 참조하세요.](../get-help-with-domains/dns-basics.md)</span><span class="sxs-lookup"><span data-stu-id="cd43c-107">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    
-  <span data-ttu-id="cd43c-108">일부 DNS 호스팅 공급자는 필수 레코드 유형을 모두 만들 수 없습니다. 이로 인해 호스팅 공급자가 [SRV, CNAME, TXT](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)또는 리디렉션을 지원하지 않는 경우 서비스 제한이 발생하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd43c-108">Some DNS hosting providers don't let you create all the required record types, which causes [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> <span data-ttu-id="cd43c-109">공급자가 SRV, TXT 또는 CNAME 레코드를 지원하지 않는 [](../get-help-with-domains/buy-a-domain-name.md) 경우 필요한 모든 레코드 형식을 지원하는 공급자로 도메인을 전송하는 [것이 좋습니다.](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)</span><span class="sxs-lookup"><span data-stu-id="cd43c-109">If your provider doesn't support SRV, TXT, or CNAME records, we recommend that you [transfer your domain](../get-help-with-domains/buy-a-domain-name.md) to a [provider that supports all required record types](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> 
    
- <span data-ttu-id="cd43c-110">필요한 DNS 레코드를 보고 전자 메일의 MX 레코드를 포함하여 각 레코드에 사용할 값을 찾으면 DNS 레코드를 만드는 데 필요한 Office 365 [참조하세요.](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="cd43c-110">To see which DNS records are required and find the values to use for each record, including the MX record for email, see [Gather the information you need to create Office 365 DNS records](../get-help-with-domains/information-for-dns-records.md).</span></span> <span data-ttu-id="cd43c-111">DNS 레코드의 기능 설명은 [DNS 기본 을 참조하세요.](../get-help-with-domains/dns-basics.md)</span><span class="sxs-lookup"><span data-stu-id="cd43c-111">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
