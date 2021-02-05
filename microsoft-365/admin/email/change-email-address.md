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
description: '초기 전자 메일 주소를 전자 메일 주소와 같은 친숙한 전자 메일 주소로 tom@fourthcoffee.com. 이렇게하려면 도메인 이름을 구입하여 Microsoft 365에 추가해야 합니다. '
ms.openlocfilehash: 445b78f759cee79a794f9656afd5b26051534e26
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114024"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>사용자 지정 도메인을 사용하도록 전자 메일 주소 변경

::: moniker range="o365-21vianet"

> [!NOTE]
> 관리 센터가 변경되고 있습니다. 사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)를 참조하세요.

::: moniker-end

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요. 
  
::: moniker range="o365-worldwide"

Microsoft 365의 초기 전자 메일 주소에는 .onmicrosoft.com(tom@fourthcoffee.onmicrosoft.com. 이는 tom@fourthcoffee.com과 같이 보다 친숙한 주소로 변경할 수 있습니다. 먼저 fourthcoffee.com과 같은 고유한 도메인 이름이 필요합니다. 도메인 이름이 이미 있는 경우 해당 도메인을 사용해도 됩니다. 그렇지 않은 경우 [도메인 등록 기관에서 도메인을 구입](../get-help-with-domains/buy-a-domain-name.md)하는 방법에 대해 알아보세요.

::: moniker-end

::: moniker range="o365-germany"

Office 365 Germany의 초기 전자 메일 주소에는 .onmicrosoft.de(tom@fourthcoffee.onmicrosoft.de. You can change it to a friendlier address like tom@fourthcoffee.de. 먼저 도메인 이름과 같은 자체 도메인 fourthcoffee.de 합니다. 도메인 이름이 이미 있는 경우 해당 도메인을 사용해도 됩니다. 그렇지 않은 경우 [도메인 등록 기관에서 도메인을 구입](../get-help-with-domains/buy-a-domain-name.md)하는 방법에 대해 알아보세요.

::: moniker-end

::: moniker range="o365-21vianet"

21Vianet에서 운영하는 Office 365의 초기 전자 메일 주소에는 partner.onmschina.cn 같은 tom@fourthcoffee.partner.onmschina.cn. 사용자와 같은 더 친한 주소로 변경할 수 tom@fourthcoffee.cn. 먼저 도메인 이름과 같은 자체 도메인 fourthcoffee.cn 합니다. 도메인 이름이 이미 있는 경우 해당 도메인을 사용해도 됩니다. 그렇지 않은 경우 [도메인 등록 기관에서 도메인을 구입](../get-help-with-domains/buy-a-domain-name.md)하는 방법에 대해 알아보세요.

::: moniker-end

When you change your domain's email to come to Microsoft 365, by updating your domain's MX record during setup, ALL email sent to that domain will start coming to Microsoft 365. MX 레코드를 변경하기 전에 도메인에 전자 메일이 있는 모든 사용자에 대해 Microsoft 365에서 사용자를 추가하고 사서함을 만들었다고 합니다. 도메인의 모든 사용자에 대한 전자 메일을 Microsoft 365로 이동하고 싶지 않은가요? 대신 몇 가지 전자 메일 주소만 사용하여 [Microsoft 365를](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain?view=o365-worldwide)시험해 볼 수 있습니다.
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터를 사용하여 사용자 지정 도메인을 사용하기 위해 전자 메일 주소 변경

이러한 단계를 수행하려면 전역 관리자 계정이 있어야 합니다. 

::: moniker range="o365-worldwide"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다. 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 의 관리 센터로 이동합니다. 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. 의 관리 센터로 이동하세요. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a> 

::: moniker-end 

2. 설치 도메인   >  **페이지로** 이동합니다. 

3. **도메인** 페이지에서 **도메인 추가** 를 선택합니다.
    
4. 단계를 따라 도메인 소유 여부를 확인하고 전자 메일 주소를 변경합니다.
    
Microsoft 365에서 도메인을 올바르게 설정하는 모든 것이 안내됩니다.

> [!NOTE]
> Exchange 라이선스를 사용하지 않는 경우 해당 도메인을 사용하여 Microsoft 365 테넌트에서 전자 메일을 보내거나 받을 수 없습니다.
  
## <a name="related-articles"></a>관련 문서

[Microsoft 365를 사용하여 사용자 지정 도메인 구입](../get-help-with-domains/buy-a-domain-name.md)
 
