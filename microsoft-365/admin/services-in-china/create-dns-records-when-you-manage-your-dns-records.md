---
title: DNS 레코드를 관리할 때 Office 365에 대 한 DNS 레코드 만들기
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
description: 'DNS 레코드 관리 시 21Vianet에서 운영 하는 Office 365에 대 한 DNS 레코드를 만드는 방법에 대해 알아봅니다. '
monikerRange: o365-21vianet
ms.openlocfilehash: 8f252ba47fbd72f5a628a23567addcc84604fb3c
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644822"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a>DNS 레코드를 관리할 때 Office 365에 대 한 DNS 레코드 만들기

메일 라우팅에 필요한 MX 레코드를 포함 하 여 21Vianet에서 운영 하는 Office 365에 대 한 DNS 레코드를 만드는 방법에 대 한 자세한 내용은 dns [호스팅 공급자에서 office 365에](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)대 한 Dns 레코드 만들기를 참조 하십시오. 
  
  
추가 옵션 및 몇 가지 알아야 할 사항:
      
-  사용 중인 도메인의 DNS 호스팅 공급자 또는 도메인 등록 기관을 모르는 경우 [도메인 등록자 또는 DNS 호스팅 공급자 찾기](../get-help-with-domains/find-your-domain-registrar.md)를 참조하세요. DNS 레코드가 수행 하는 작업에 대 한 설명은 [dns 기본 사항을](../get-help-with-domains/dns-basics.md)참조 하세요.
    
-  일부 DNS 호스팅 공급자는 필요한 모든 레코드 형식을 만들 수 없으므로 [호스팅 공급자가 SRV, CNAME, TXT 또는 리디렉션을 지원 하지 않는 경우 서비스 제한이](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)발생 합니다. 공급자가 SRV, TXT 또는 CNAME 레코드를 지원 하지 않는 경우에는 [필요한 모든 레코드 종류를 지 원하는 공급자](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)에 게 [도메인을 전송](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/buy-a-domain-name) 하는 것이 좋습니다. 
    
- 필요한 DNS 레코드를 확인 하 고 전자 메일에 대 한 MX 레코드를 포함 하 여 각 레코드에 사용할 값을 찾으려면 [Office 365 DNS 레코드를 만드는 데 필요한 정보 수집](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records)을 참조 하십시오. DNS 레코드가 수행 하는 작업에 대 한 설명은 [dns 기본 사항을](../get-help-with-domains/dns-basics.md)참조 하세요.
    

