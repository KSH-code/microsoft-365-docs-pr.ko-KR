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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: 도메인 이름을 구입하고 도메인에 tom@fourthcoffee.com 전자 메일 주소와 같은 친숙한 전자 메일 주소로 Microsoft 365.
ms.openlocfilehash: 599ca47a9df2dc7b022ff614e3f78b23defdd96e
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59184764"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>사용자 지정 도메인을 사용하도록 전자 메일 주소 변경

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요. 
  
::: moniker range="o365-worldwide"

Microsoft 365 전자 메일 주소에는 .onmicrosoft.com 포함됩니다(tom@fourthcoffee.onmicrosoft.com. 이는 tom@fourthcoffee.com과 같이 보다 친숙한 주소로 변경할 수 있습니다. 먼저 fourthcoffee.com과 같은 고유한 도메인 이름이 필요합니다. 도메인 이름이 이미 있는 경우 해당 도메인을 사용해도 됩니다. 그렇지 않은 경우 [도메인 등록 기관에서 도메인을 구입](../get-help-with-domains/buy-a-domain-name.md)하는 방법에 대해 알아보세요.

::: moniker-end

::: moniker range="o365-germany"

독일의 초기 전자 메일 주소에는 Office 365 .onmicrosoft.de 포함됩니다(tom@fourthcoffee.onmicrosoft.de. 사용자와 같은 더 친한 주소로 변경할 tom@fourthcoffee.de. 먼저 도메인 이름과 같은 도메인 fourthcoffee.de 필요합니다. 도메인 이름이 이미 있는 경우 해당 도메인을 사용해도 됩니다. 그렇지 않은 경우 [도메인 등록 기관에서 도메인을 구입](../get-help-with-domains/buy-a-domain-name.md)하는 방법에 대해 알아보세요.

::: moniker-end

::: moniker range="o365-21vianet"

21Vianet에서 운영하는 Office 365 전자 메일 주소에는 21Vianet과 같은 partner.onmschina.cn 포함되어 tom@fourthcoffee.partner.onmschina.cn. 사용자와 같은 더 친한 주소로 변경할 tom@fourthcoffee.cn. 먼저 도메인 이름과 같은 도메인 fourthcoffee.cn 필요합니다. 도메인 이름이 이미 있는 경우 해당 도메인을 사용해도 됩니다. 그렇지 않은 경우 [도메인 등록 기관에서 도메인을 구입](../get-help-with-domains/buy-a-domain-name.md)하는 방법에 대해 알아보세요.

::: moniker-end

설정하는 동안 도메인의 MX 레코드를 업데이트하여 도메인의 Microsoft 365 변경하면 해당 도메인으로 전송된 모든 전자 메일이 Microsoft 365. MX 레코드를 변경하기 전에 도메인에 전자 메일을 Microsoft 365 사용자를 추가하고 사서함을 만들어야 합니다. 도메인의 모든 사용자가 전자 메일을 전자 메일로 이동하지 Microsoft 365? 대신 몇 가지 전자 [메일 Microsoft 365 사용하여 파일럿을 수행하기](../misc/pilot-microsoft-365-from-my-custom-domain.md)위한 단계를 취할 수 있습니다.
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>전자 메일 주소를 변경하여 사용자 지정 도메인을 Microsoft 365 관리 센터

다음 단계를 수행하려면 전역 관리자여야 합니다.

::: moniker range="o365-worldwide"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다.

::: moniker-end

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>의 관리 센터로 이동합니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 의 관리 센터로 이동하세요. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>

::: moniker-end

2. 설치 도메인   >  **페이지로** 이동합니다.

3. **도메인** 페이지에서 **도메인 추가** 를 선택합니다.

4. 단계에 따라 도메인을 소유하고 있는지 확인할 수 있습니다. You'll be guided to get everything set up correctly with your domain in Microsoft 365.

5. 사용자 활성  >  **사용자로 이동 합니다.**

6. 사용자를 선택하여 사용자 이름을 편집하고 방금 추가한 도메인으로 변경합니다.

> [!NOTE]
> Exchange 라이선스를 사용하지 않는 경우 도메인을 사용하여 Microsoft 365 테넌트에서 전자 메일을 보내거나 받을 수 없습니다.
  
## <a name="related-content"></a>관련 콘텐츠

[사용자 지정 도메인을 사용하여](../get-help-with-domains/buy-a-domain-name.md) 사용자 지정 도메인 Microsoft 365(문서)\
[도메인 관리(링크](../get-help-with-domains/index.yml) 페이지)\
[도메인 FAQ](../setup/domains-faq.yml) (문서)