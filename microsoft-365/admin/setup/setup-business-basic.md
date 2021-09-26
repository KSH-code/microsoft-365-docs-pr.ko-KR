---
title: Microsoft 365 Business Basic 설정
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_O365_Setup
- TRN_SMB
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
- MOE150
- BEA160
description: Microsoft 365 Business Basic 구독을 설정하는 방법을 알아보세요.
ms.openlocfilehash: ba751d41ddc519e1c75d4783df145e6b9854c985
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "59773718"
---
# <a name="set-up-microsoft-365-business-basic"></a>Microsoft 365 Business Basic 설정

## <a name="watch-set-up-microsoft-365-business-basic"></a>시청: Microsoft 365 Business Basic 설정

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vk3W]

이 비디오가 도움이 된 경우에는 [소규모 비즈니스와 Microsoft 365를 처음 사용하는 사용자를 위한 완전한 교육 시리즈](../../business-video/index.yml)를 참조하세요.

## <a name="add-your-domain-to-personalize-sign-in"></a>로그인 개인 설정을 위한 도메인 추가

Microsoft 365 Business Basic을 구입하면 사용자가 소유하고 있는 도메인을 사용하거나 등록할 때 도메인을 구입하는 옵션이 제공됩니다.

- 등록할 때 새 도메인을 구입하면 도메인이 모두 설정되어 [사용자 추가 및 라이선스를 할당](#add-users-and-assign-licenses)으로 이동할 수 있습니다.

 ::: moniker range="o365-worldwide"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다.

::: moniker-end

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>의 관리 센터로 이동합니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>의 관리 센터로 이동합니다.

::: moniker-end 

2. **설정으로 이동** 을 선택해 마법사를 시작합니다.
    
3. **도메인 추가** 단계에서 사용할 도메인 이름(예: contoso.com)을 입력합니다.

    > [!IMPORTANT]
    > 등록할 때 도메인을 구입한 경우에는 **도메인 추가** 단계가 표시되지 않습니다. 대신 [사용자 추가](#add-users-and-assign-licenses)로 이동하세요.

    
4. 마법사의 단계에 따라 도메인을 소유하고 있는지 확인하는 [DNS 호스팅 공급자에 상관없이 Office 365용 DNS 레코드 만들기](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)를 완료합니다. 도메인 호스트를 알고 있는 경우 [Microsoft 365에 도메인 추가](/microsoft-365/admin/setup/add-domain)도 참조하세요.

    호스팅 공급자가 GoDaddy이거나 [도메인 연결](/office365/admin/get-help-with-domains/domain-connect)을 사용하는 다른 호스트를 사용하는 경우에는 프로세스가 간단하며, 자동으로 로그인하라는 메시지가 표시되고 Microsoft가 사용자를 대신하여 인증하도록 합니다.

    ![GoDaddy 액세스 확인 페이지에서 승인을 선택합니다.](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a>사용자 추가 및 라이선스 할당

마법사에서 사용자를 추가하거나 관리 센터에서 [나중에 사용자를 추가](../add-users/add-users.md)할 수도 있습니다. 또한 로컬 도메인 컨트롤러를 사용하는 경우 [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express)를 사용하여 사용자를 추가할 수 있습니다.

## <a name="add-users-in-the-wizard"></a>마법사에서 사용자 추가

마법사에서 추가한 모든 사용자에게 자동으로 Microsoft 365 Business Basic 라이선스가 할당됩니다.

1. Microsoft 365 Business Basic 구독에 기존 사용자가 있는 경우(예를 들어 Azure AD Connect를 사용한 경우) 해당 사용자에게 라이선스를 할당하는 옵션이 여기에 표시됩니다. 해당 사용자에게도 라이선스를 추가합니다.

2. 사용자를 추가한 후에는 새로 추가한 사용자와 자격 증명을 공유하는 옵션도 여기에 표시됩니다. 자격 증명을 인쇄, 전자 메일로 전송 또는 다운로드할 수 있습니다.

## <a name="connect-your-domain"></a>도메인 연결

> [!NOTE]
> .onmicrosoft 도메인을 사용하거나 Azure AD Connect를 사용하여 사용자를 설정하는 경우에는 이 단계가 표시되지 않습니다.
  
서비스를 설정하려면 DNS 호스트 또는 도메인 등록 기관에서 레코드를 업데이트해야 합니다.
  
1. 설정 마법사는 일반적으로 사용자의 등록 기관을 감지하여 등록 기관 웹 사이트에서 NS 레코드를 업데이트하기 위한 단계별 지침의 링크를 제공합니다. 링크를 제공받지 못한 경우에는 [도메인 등록 기관에서 이름 서버를 변경하여 Office 365 설정](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md)을 합니다. 

    - 기존 웹 사이트와 같은 기존 DNS 레코드를 사용하지만 DNS 호스트를 [도메인 연결](/office365/admin/get-help-with-domains/domain-connect)에서 사용할 수 있는 경우 **레코드 추가** 를 선택 합니다. **온라인 서비스 선택** 페이지에서 모든 기본값을 적용하고 **다음** 을 선택한 후 DNS 호스트의 페이지에서 **승인** 을 선택합니다.
    - 도메인 연결 사용이 설정되지 않은 다른 DNS 호스트에서 기존 DNS 레코드를 사용하는 경우 기존 서비스를 계속 연결할 수 있도록 DNS 레코드를 관리하는 것이 좋습니다. 자세한 내용은 [도메인 기본 사항](/office365/admin/get-help-with-domains/dns-basics)을 참조하세요.

2. 마법사의 단계를 따르면 전자 메일 및 기타 서비스가 설정됩니다.

    등록 프로세스가 완료되면 관리 센터로 이동하여 사용자를 추가하고 라이선스를 할당합니다. 초기 설정을 완료한 후 관리 센터의 **설정** 페이지를 사용하여 구독과 함께 제공되는 서비스를 계속 설정하고 구성할 수 있습니다.

    설정 마법사와 관리 센터 **설정** 페이지에 대한 자세한 내용은 [설정 마법사와 설정 페이지의 차이점](o365-setup-wizard-and-setup-page.md)을 참조하세요.