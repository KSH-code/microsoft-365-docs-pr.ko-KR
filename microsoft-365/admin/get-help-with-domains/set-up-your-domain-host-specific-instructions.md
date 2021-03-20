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
# <a name="set-up-your-domain-host-specific-instructions"></a>도메인 설정(호스트별 지침)

Microsoft 365에서 사용자 지정 도메인(contoso.com)을 사용하려면 도메인을 확인하고 도메인의 DNS 레코드를 구성해야 합니다. 
  
도메인 호스트의 관리 도구를 사용하여 DNS 레코드를 추가 및 관리하거나 Microsoft에 도메인 레코드에 대한 제어를 제공하면 해당 레코드가 설정됩니다.
  
정확한 단계는 아래에서 도메인 호스트를 선택합니다. 호스트가 누구에게 있는지 확실하지 않은 경우 도메인 등록 기관 [찾기를 참조합니다.](find-your-domain-registrar.md)
  

## <a name="let-microsoft-365-manage-your-dns-records"></a>Microsoft 365에서 DNS 레코드 관리

||
|---|---|
|[1&1 IONOS](../dns/change-nameservers-at-1-1-internet.md) |
|[AWS(Amazon Web Services)](../dns/change-nameservers-at-aws.md) |
 [Bluehost](../dns/change-nameservers-at-bluehost.md)|
|[Google Domains](../dns/change-nameservers-at-google-domains.md) |
|[Hostgator   ](../dns/change-nameservers-at-hostgator.md)  |  
|[MyDomain](../dns/change-nameservers-at-mydomain.md) | 
|[Namecheap](../dns/change-nameservers-at-namecheap.md)|
|[Network Solutions](../dns/change-nameservers-at-network-solutions.md) |  

또는 도메인 등록 기관에서 이름 서퍼를 변경하여 [Microsoft 365를 설정하는 방법을 배워야 합니다.](change-nameservers-at-any-domain-registrar.md)

## <a name="manage-your-own-dns-records"></a>자체 DNS 레코드 관리

|                           |                          |
|---------------------------|--------------------------|
| [1&1 IONOS](../dns/create-dns-records-at-1-1-internet.md) | [호버](./create-dns-records-at-any-dns-hosting-provider.md) |
| [123-reg.co.uk](../dns/create-dns-records-at-123-reg-co-uk.md) | [Google에서 관리(eNom)](../dns/create-dns-records-for-domain-managed-by-google-enom.md)|
| [AWS(Amazon Web Services)](../dns/create-dns-records-at-aws.md) | [MyDomain](../dns/create-dns-records-at-mydomain.md) |
| [Azure DNS 영역](../dns/create-dns-records-for-azure-dns-zones.md) | [name.com](../dns/create-dns-records-at-name-com.md) |
| [Bluehost](../dns/create-dns-records-at-bluehost.md) | [Namecheap](../dns/create-dns-records-at-namecheap.md)|
| [Cloudflare](../dns/create-dns-records-at-cloudflare.md)| [Names.co.uk](../dns/create-dns-records-at-names-co-uk.md) |
|  [Crazy Domains](../dns/create-dns-records-at-crazy-domains.md)| [Netregistry](../dns/create-dns-records-at-netregistry.md) |
|[DNSMadeEasy](../dns/create-dns-records-at-dnsmadeeasy.md) | [네트워크 솔루션](../dns/create-dns-records-at-network-solutions.md) |
|[에코스트](../dns/create-dns-records-at-dreamhost.md)  | [OVH](../dns/create-dns-records-at-ovh.md) |
|  [Dyn.com](../dns/create-dns-records-at-dyn-com.md) | [Register.com](../dns/create-dns-records-at-register-com.md) |
| [eNomCentral](../dns/create-dns-records-at-enomcentral.md)| [Microsoft 365용 Register365](../dns/create-dns-records-at-register365.md)  |
| [Freenom](../dns/create-dns-records-at-freenom.md) | [ web.com ](../dns/create-dns-records-at-web-com.md)|
|[GoDaddy](../dns/create-dns-records-at-godaddy.md)|[ Windows 기반 DNS](../dns/create-dns-records-using-windows-based-dns.md)   |
| [Google 도메인](../dns/create-dns-records-at-google-domains.md) |[Wix](../dns/create-dns-records-at-wix.md) |
|[Hostgator](../dns/create-dns-records-at-hostgator.md)  | [Yahoo!   Small Business](../dns/create-dns-records-at-yahoo-small-business.md)  |

[도메인 호스트가 이 목록에 없는 경우 일반 지침이 필요합니다. ](create-dns-records-at-any-dns-hosting-provider.md)
