---
title: 사용자 지정 도메인을 사용하도록 전자 메일 주소 변경
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
description: '초기 전자 메일 주소를 예를 위한 전자 메일 주소와 tom@fourthcoffee.com. 이렇게 하려면 도메인 이름을 버리한 후 Microsoft 365에 추가해야 합니다. '
ms.openlocfilehash: dc6d418961fe29a363aa6a787d8c0bb2d11d7e97
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814483"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>사용자 지정 도메인을 사용하도록 전자 메일 주소 변경

::: moniker range="o365-21vianet"

> [!NOTE]
> 관리 센터가 변경되고 있습니다. 사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.

::: moniker-end

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요. 
  
::: moniker range="o365-worldwide"

Microsoft 365의 초기 전자 메일 주소에는 .onmicrosoft.com(예: i/tom@fourthcoffee.onmicrosoft.com). 이는 tom@fourthcoffee.com과 같이 보다 친숙한 주소로 변경할 수 있습니다. 먼저 fourthcoffee.com과 같은 고유한 도메인 이름이 필요합니다. 도메인 이름이 이미 있는 경우 해당 도메인을 사용해도 됩니다. 그렇지 않은 경우 [도메인 등록 기관에서 도메인을 구입](../get-help-with-domains/buy-a-domain-name.md)하는 방법에 대해 알아보세요.

::: moniker-end

::: moniker range="o365-germany"

Office 365 Germany의 초기 전자 메일 주소에는 .onmicrosoft.de(예: tom@fourthcoffee.onmicrosoft.de. 리소스 업데이트를 필요한 번호와 같은 친숙한 주소로 변경할 tom@fourthcoffee.de. You'll need your own domain name, like fourthcoffee.de. 도메인 이름이 이미 있는 경우 해당 도메인을 사용해도 됩니다. 그렇지 않은 경우 [도메인 등록 기관에서 도메인을 구입](../get-help-with-domains/buy-a-domain-name.md)하는 방법에 대해 알아보세요.

::: moniker-end

::: moniker range="o365-21vianet"

21Vianet에서 운영하는 Office 365의 초기 전자 메일 주소에는 사서함이 partner.onmschina.cn 예: 위와 tom@fourthcoffee.partner.onmschina.cn. You can change it to a friender address like tom@fourthcoffee.cn. You'll need your own domain name, like fourthcoffee.cn first. 도메인 이름이 이미 있는 경우 해당 도메인을 사용해도 됩니다. 그렇지 않은 경우 [도메인 등록 기관에서 도메인을 구입](../get-help-with-domains/buy-a-domain-name.md)하는 방법에 대해 알아보세요.

::: moniker-end

설치 중 도메인의 MX 레코드를 업데이트하여 도메인의 전자 메일을 Microsoft 365로 변경하면 해당 도메인으로 전송된 모든 전자 메일이 Microsoft 365로 제공하기 시작합니다. MX 레코드를 변경하기 전에 해당 도메인에 전자 메일이 있는 모든 사용자에 대해 Microsoft 365에서 사용자를 추가하고 사서함을 만들었는지 확인합니다. 도메인에 있는 모든 사용자의 전자 메일을 Microsoft 365로 이동하고자 하나요? 대신 몇 개의 전자 메일 [주소만 사용하여 Microsoft 365 시험 사용 을 스크롤하는 단계를 수행할 수 있습니다.](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain?view=o365-worldwide)
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터를 사용하여 사용자 지정 도메인을 사용하도록 전자 메일 주소 변경

다음 단계를 수행하려면 전역 관리자 계정이 필요합니다. 

::: moniker range="o365-worldwide"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다. 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 의 관리 센터로 이동합니다. 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터로 이동합니다. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a> 

::: moniker-end 

2. 설정 도메인 **페이지로**  >  **이동합니다.** 

3. **도메인** 페이지에서 **도메인 추가**를 선택합니다.
    
4. 단계를 따라 도메인 소유 여부를 확인하고 전자 메일 주소를 변경합니다.
    
Microsoft 365에서 도메인을 올바르게 설정하는 데 필요한 모든 지침이 있습니다.

> [!NOTE]
> Exchange 라이선스를 사용하지 않는 경우에는 해당 도메인을 사용하여 Microsoft 365 테넌트의 전자 메일을 보내거나 받을 수 없습니다.
  
## <a name="related-articles"></a>관련 문서

[Microsoft 365를 사용하여 사용자 지정 도메인 만들기](../get-help-with-domains/buy-a-domain-name.md)
 
