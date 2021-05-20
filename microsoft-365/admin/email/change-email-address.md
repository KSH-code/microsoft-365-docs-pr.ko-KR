---
title: 사용자 지정 도메인을 사용하도록 전자 메일 주소 변경
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
- Adm_O365_Setup
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: 도메인 이름을 구입하고 Microsoft 365 추가하여 tom@fourthcoffee.com 같은 친숙한 이메일 주소로 이메일 주소를 변경합니다.
ms.openlocfilehash: d5e70856c9200cd7e5df0eded25b6ff460e5d1fe
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572096"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>사용자 지정 도메인을 사용하도록 전자 메일 주소 변경

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요. 
  
::: moniker range="o365-worldwide"

Microsoft 365 초기 이메일 주소에는 tom@fourthcoffee.onmicrosoft.com 같은 .onmicrosoft.com 포함됩니다. 이는 tom@fourthcoffee.com과 같이 보다 친숙한 주소로 변경할 수 있습니다. 먼저 fourthcoffee.com과 같은 고유한 도메인 이름이 필요합니다. 도메인 이름이 이미 있는 경우 해당 도메인을 사용해도 됩니다. 그렇지 않은 경우 [도메인 등록 기관에서 도메인을 구입](../get-help-with-domains/buy-a-domain-name.md)하는 방법에 대해 알아보세요.

::: moniker-end

::: moniker range="o365-germany"

독일의 초기 이메일 주소에는 tom@fourthcoffee.onmicrosoft.de 같은 .onmicrosoft.de Office 365. tom@fourthcoffee.de 같은 친숙한 주소로 변경할 수 있습니다. 먼저 fourthcoffee.de 같은 고유한 도메인 이름이 필요합니다. 도메인 이름이 이미 있는 경우 해당 도메인을 사용해도 됩니다. 그렇지 않은 경우 [도메인 등록 기관에서 도메인을 구입](../get-help-with-domains/buy-a-domain-name.md)하는 방법에 대해 알아보세요.

::: moniker-end

::: moniker range="o365-21vianet"

21Vianet이 운영하는 Office 365 초기 이메일 주소에는 tom@fourthcoffee.partner.onmschina.cn 같은 partner.onmschina.cn 포함합니다. tom@fourthcoffee.cn 같은 친숙한 주소로 변경할 수 있습니다. 먼저 fourthcoffee.cn 같은 고유한 도메인 이름이 필요합니다. 도메인 이름이 이미 있는 경우 해당 도메인을 사용해도 됩니다. 그렇지 않은 경우 [도메인 등록 기관에서 도메인을 구입](../get-help-with-domains/buy-a-domain-name.md)하는 방법에 대해 알아보세요.

::: moniker-end

도메인의 이메일을 Microsoft 365 변경하면 설정 중에 도메인의 MX 레코드를 업데이트하여 해당 도메인으로 전송된 모든 이메일이 Microsoft 365 시작됩니다. MX 레코드를 변경하기 전에 도메인에 전자 메일이 있는 모든 사용자를 Microsoft 365 사용자를 추가하고 사서함을 만졌는지 확인합니다. 도메인의 모든 사용자가 Microsoft 365 이메일을 이동하지 않으려면? 대신 몇 개의 [이메일 주소만 으로 Microsoft 365 파일럿하는](../misc/pilot-microsoft-365-from-my-custom-domain.md)단계를 수행할 수 있습니다.
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터를 사용하여 사용자 지정 도메인을 사용하도록 이메일 주소를 변경

이러한 단계를 수행하려면 전역 관리자 계정이 있어야 합니다. 

::: moniker range="o365-worldwide"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>의 관리 센터로 이동합니다. 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>의 관리 센터로 이동합니다. 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>에서 관리 센터로 이동합니다. 

::: moniker-end 

2. **설정**  >  **도메인 페이지로 이동합니다.** 

3. **도메인** 페이지에서 **도메인 추가** 를 선택합니다.
    
4. 단계를 따라 도메인 소유 여부를 확인하고 전자 메일 주소를 변경합니다.
    
Microsoft 365 도메인을 사용하여 모든 것을 올바르게 설정하도록 안내받게 됩니다.

> [!NOTE]
> Exchange 라이선스를 사용하지 않는 경우 도메인을 사용하여 Microsoft 365 테넌트에서 이메일을 보내거나 받을 수 없습니다.
  
## <a name="related-content"></a>관련 콘텐츠

[Microsoft 365 사용하여 사용자 지정 도메인](../get-help-with-domains/buy-a-domain-name.md) 구매(기사)
