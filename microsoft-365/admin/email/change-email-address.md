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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: '초기 전자 메일 주소를 tom@fourthcoffee.com와 같은 친숙 한 전자 메일 주소로 변경 합니다. 이 작업을 수행 하려면 도메인 이름을 구입 하 여 Microsoft 365에 추가 해야 합니다. '
ms.openlocfilehash: 50739c01fda9528140870798324dd69a1c68abce
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140503"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>사용자 지정 도메인을 사용하도록 전자 메일 주소 변경

::: moniker range="o365-21vianet"

> [!NOTE]
> 관리 센터가 변경 되는 중입니다. 환경이 여기에 나와 있는 세부 정보와 일치 하지 않으면 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조 하세요.

::: moniker-end

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요. 
  
::: moniker range="o365-worldwide"

Microsoft 365의 초기 전자 메일 주소에는 tom@fourthcoffee.onmicrosoft.com와 같은 onmicrosoft.com이 포함 되어 있습니다. 이는 tom@fourthcoffee.com과 같이 보다 친숙한 주소로 변경할 수 있습니다. 먼저 fourthcoffee.com과 같은 고유한 도메인 이름이 필요합니다. 도메인 이름이 이미 있는 경우 해당 도메인을 사용해도 됩니다. 그렇지 않은 경우 [도메인 등록 기관에서 도메인을 구입](../get-help-with-domains/buy-a-domain-name.md)하는 방법에 대해 알아보세요.

::: moniker-end

::: moniker range="o365-germany"

Office 365 독일의 초기 전자 메일 주소에는 tom@fourthcoffee.onmicrosoft.de와 같은 onmicrosoft.de이 포함 되어 있습니다. Tom@fourthcoffee.de와 같은 보다 친숙 한 주소로 변경할 수 있습니다. 먼저 fourthcoffee.de과 같은 고유한 도메인 이름이 필요 합니다. 도메인 이름이 이미 있는 경우 해당 도메인을 사용해도 됩니다. 그렇지 않은 경우 [도메인 등록 기관에서 도메인을 구입](../get-help-with-domains/buy-a-domain-name.md)하는 방법에 대해 알아보세요.

::: moniker-end

::: moniker range="o365-21vianet"

21Vianet에서 운영 하는 Office 365의 초기 전자 메일 주소에는 tom@fourthcoffee.partner.onmschina.cn와 같은 partner.onmschina.cn 포함 되어 있습니다. Tom@fourthcoffee.cn와 같은 보다 친숙 한 주소로 변경할 수 있습니다. 먼저 fourthcoffee.cn과 같은 고유한 도메인 이름이 필요 합니다. 도메인 이름이 이미 있는 경우 해당 도메인을 사용해도 됩니다. 그렇지 않은 경우 [도메인 등록 기관에서 도메인을 구입](../get-help-with-domains/buy-a-domain-name.md)하는 방법에 대해 알아보세요.

::: moniker-end

설치 하는 동안 도메인의 MX 레코드를 업데이트 하 여 도메인의 전자 메일을 Microsoft 365로 변경 하면 해당 도메인으로 전송 되는 모든 전자 메일이 Microsoft 365로 시작 됩니다. MX 레코드를 변경 하기 전에 도메인에 전자 메일이 있는 모든 사용자가 Microsoft 365에서 사용자를 추가 하 고 사서함을 만들었는지 확인 합니다. 도메인의 모든 사용자에 대 한 전자 메일을 Microsoft 365로 이동 하지 않으려고 하나요? [대신 몇 개의 전자 메일 주소만 사용 하 여 Microsoft 365를 파일럿 하는](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)단계를 수행할 수 있습니다.
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터를 사용 하 여 사용자 지정 도메인을 사용 하도록 전자 메일 주소 변경

이 단계를 수행 하려면 전역 관리자 계정이 있어야 합니다. 

::: moniker range="o365-worldwide"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다. 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 의 관리 센터로 이동합니다. 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>()로 이동 합니다. 

::: moniker-end 

2. **도메인** **설정** > 페이지로 이동 합니다. 

3. **도메인** 페이지에서 **도메인 추가**를 선택 합니다.
    
4. 단계를 따라 도메인 소유 여부를 확인하고 전자 메일 주소를 변경합니다.
    
Microsoft 365에서 도메인에 대 한 모든 기능을 올바르게 설정 하는 방법을 안내 합니다.

> [!NOTE]
> Exchange 라이선스를 사용 하지 않는 경우에는 도메인을 사용 하 여 Microsoft 365 테 넌 트에서 전자 메일을 보내거나 받을 수 없습니다.
  
## <a name="related-articles"></a>관련 문서

[Microsoft 365을 사용 하 여 사용자 지정 도메인 구입](../get-help-with-domains/buy-a-domain-name.md)
 
