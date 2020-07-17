---
title: DNS 레코드를 관리할 때 Office 365에 대 한 DNS 레코드 만들기
f1.keywords:
- CSH
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEA150
ms.assetid: 0669bf14-414d-4f51-8231-6b710ce7980b
ROBOTS: NOINDEX
description: 'DNS 레코드 관리 시 21Vianet에서 운영 하는 Office 365에 대 한 DNS 레코드를 만드는 방법에 대해 알아봅니다. '
monikerRange: o365-21vianet
ms.openlocfilehash: c05dc1c84465ea06572021610744f0cbe5aa9fea
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779908"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a><span data-ttu-id="0a459-103">DNS 레코드를 관리할 때 Office 365에 대 한 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="0a459-103">Create DNS records for Office 365 when you manage your DNS records</span></span>

<span data-ttu-id="0a459-104">메일 라우팅에 필요한 MX 레코드를 포함 하 여 21Vianet에서 운영 하는 Office 365에 대 한 DNS 레코드를 만드는 방법에 대 한 자세한 내용은 dns [호스팅 공급자에서 office 365에](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)대 한 Dns 레코드 만들기를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0a459-104">For detailed instructions about how to create DNS records for Office 365 operated by 21Vianet, including the MX record required for mail routing, see [Create DNS records at any DNS hosting provider for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> 
  
  
<span data-ttu-id="0a459-105">추가 옵션 및 몇 가지 알아야 할 사항:</span><span class="sxs-lookup"><span data-stu-id="0a459-105">More options and some things to be aware of:</span></span>
      
-  <span data-ttu-id="0a459-106">사용 중인 도메인의 DNS 호스팅 공급자 또는 도메인 등록 기관을 모르는 경우 [도메인 등록자 또는 DNS 호스팅 공급자 찾기](../get-help-with-domains/find-your-domain-registrar.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0a459-106">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span> <span data-ttu-id="0a459-107">DNS 레코드가 수행 하는 작업에 대 한 설명은 [dns 기본 사항을](../get-help-with-domains/dns-basics.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0a459-107">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    
-  <span data-ttu-id="0a459-108">일부 DNS 호스팅 공급자는 필요한 모든 레코드 형식을 만들 수 없으므로 [호스팅 공급자가 SRV, CNAME, TXT 또는 리디렉션을 지원 하지 않는 경우 서비스 제한이](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a459-108">Some DNS hosting providers don't let you create all the required record types, which causes [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> <span data-ttu-id="0a459-109">공급자가 SRV, TXT 또는 CNAME 레코드를 지원 하지 않는 경우에는 [필요한 모든 레코드 종류를 지 원하는 공급자](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)에 게 [도메인을 전송](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/buy-a-domain-name) 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0a459-109">If your provider doesn't support SRV, TXT, or CNAME records, we recommend that you [transfer your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/buy-a-domain-name) to a [provider that supports all required record types](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> 
    
- <span data-ttu-id="0a459-110">필요한 DNS 레코드를 확인 하 고 전자 메일에 대 한 MX 레코드를 포함 하 여 각 레코드에 사용할 값을 찾으려면 [Office 365 DNS 레코드를 만드는 데 필요한 정보 수집](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0a459-110">To see which DNS records are required and find the values to use for each record, including the MX record for email, see [Gather the information you need to create Office 365 DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records).</span></span> <span data-ttu-id="0a459-111">DNS 레코드가 수행 하는 작업에 대 한 설명은 [dns 기본 사항을](../get-help-with-domains/dns-basics.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0a459-111">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    

