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
description: 도메인 연결 사용 등록 기관으로 작업하고 Microsoft 365에 도메인을 추가하는 방법을 알아보고
ms.openlocfilehash: 109255d82100e636e3472242866a519ff64a9e54
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49655615"
---
# <a name="using-domain-connect"></a>도메인 연결 사용

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요.
  
[도메인 연결 ](https://www.domainconnect.org/) 사용 등록 기관을 사용하면 몇 분 정도 걸리는 3단계 프로세스에서 도메인을 Microsoft 365에 추가할 수 있습니다. 
  
마법사에서 도메인을 소유하고 있는 것을 확인한 다음 도메인의 레코드를 자동으로 설정하게 되며, 전자 메일이 Microsoft 365 및 Teams와 같은 기타 Microsoft 365 서비스로 전송되어 도메인과 함께 작업합니다.
  
> [!NOTE]
> 설정 마법사를 시작하기 전에 브라우저의 팝업 차단 기능을 해제하세요.
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Microsoft 365와 통합하는 도메인 연결 등록자

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer 또는 WildWestDomains(SecureServer DNS 호스팅을 사용하는 GoDaddy 리셀러)
    - [MadDog 도메인](https://www.maddogdomains.com/)
    - [CheapNames](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a>전자 메일 및 웹 사이트는 어떻게 하나요?

설치를 마친 후 도메인의 MX 레코드가 Microsoft 365를 지점으로 업데이트하고 도메인의 모든 전자 메일이 Microsoft 365로 전송됩니다. 도메인에서 전자 메일을 받는 모든 사용자에 대해 Microsoft 365에서 사용자를 추가하고 사서함을 설정해야 합니다.
  
업무에 사용하는 웹 사이트가 있는 경우 어디에 있든 작동이 유지됩니다. 도메인 연결 설정 단계는 웹 사이트에 영향을 주지 않습니다.
