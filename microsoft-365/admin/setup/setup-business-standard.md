---
title: Microsoft 365 Business Standard 설정
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
- Adm_TOC
- Adm_O365_Setup
- TRN_SMB
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
description: Microsoft 365 Business Standard를 구입하면 본인 소유 도메인을 사용하거나 가입 중 도메인을 구매할 수 있습니다.
ms.openlocfilehash: cee91edaab09506dca90cf5ed64ee9bc669c98cf
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624420"
---
# <a name="set-up-microsoft-business-standard"></a>Microsoft Business Standard 설정



## <a name="add-your-domain-to-personalize-sign-in"></a>로그인 개인 설정을 위한 도메인 추가

Microsoft 365 Business Standard를 구입하면 사용자가 소유하고 있는 도메인을 사용하거나 등록할 때 도메인을 구입하는 옵션이 제공됩니다.

- 등록할 때 새 도메인을 구입하면 도메인이 모두 설정되어 [사용자 추가 및 라이선스를 할당](#add-users-and-assign-licenses)으로 이동할 수 있습니다.

1. 전역 관리자 자격 증명을 사용하여 [Microsoft 365 관리 센터](https://admin.microsoft.com)에 로그인합니다. 

2. **설정으로 이동** 을 선택해 마법사를 시작합니다.

3. **Office 앱 설치** 페이지에서 컴퓨터에 선택적으로 앱을 설치할 수 있습니다.
    
4. **도메인 추가** 단계에서 사용할 도메인 이름(예: contoso.com)을 입력합니다.

    > [!IMPORTANT]
    > 등록할 때 도메인을 구입한 경우에는 **도메인 추가** 단계가 표시되지 않습니다. 대신 [사용자 추가](#add-users-and-assign-licenses)로 이동하세요.

    
4. 마법사의 단계에 따라 도메인을 소유하고 있는지 확인하는 [DNS 호스팅 공급자에 상관없이 Office 365용 DNS 레코드 만들기](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)를 완료합니다. 도메인 호스트를 알고 있는 경우 [호스트 관련 지침](/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)을 참조하세요.

    호스팅 공급자가 GoDaddy이거나 [도메인 연결](/office365/admin/get-help-with-domains/domain-connect)을 사용하는 다른 호스트를 사용하는 경우에는 프로세스가 간단하며, 자동으로 로그인하라는 메시지가 표시되고 Microsoft가 사용자를 대신하여 인증하도록 합니다.

    ![GoDaddy 액세스 확인 페이지에서 승인을 선택합니다.](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a>사용자 추가 및 라이선스 할당

마법사에서 사용자를 추가하거나 관리 센터에서 [나중에 사용자를 추가](../add-users/add-users.md)할 수도 있습니다. 또한 로컬 도메인 컨트롤러를 사용하는 경우 [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express)를 사용하여 사용자를 추가할 수 있습니다.

## <a name="add-users-in-the-wizard"></a>마법사에서 사용자 추가

마법사에서 추가한 모든 사용자에게 자동으로 Microsoft 365 Business Standard 라이선스가 할당됩니다.

1. Microsoft 365 Business Standard 구독에 기존 사용자가 있는 경우(예를 들어 Azure AD Connect를 사용한 경우) 해당 사용자에게 라이선스를 할당하는 옵션이 여기에 표시됩니다. 해당 사용자에게도 라이선스를 추가합니다.

2. 사용자를 추가한 후에는 새로 추가한 사용자와 자격 증명을 공유하는 옵션도 여기에 표시됩니다. 자격 증명을 인쇄, 전자 메일로 전송 또는 다운로드할 수 있습니다.

## <a name="connect-your-domain"></a>도메인 연결

> [!NOTE]
> .onmicrosoft 도메인을 사용하거나 Azure AD Connect를 사용하여 사용자를 설정하는 경우에는 이 단계가 표시되지 않습니다.
  
서비스를 설정하려면 DNS 호스트 또는 도메인 등록 기관에서 레코드를 업데이트해야 합니다.
  
1. 설정 마법사는 일반적으로 사용자의 등록 기관을 감지하여 등록 기관 웹 사이트에서 NS 레코드를 업데이트하기 위한 단계별 지침의 링크를 제공합니다. 링크를 제공받지 못한 경우에는 [도메인 등록 기관에서 이름 서버를 변경하여 Office 365 설정](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md)을 합니다. 

    - 기존 웹 사이트와 같은 기존 DNS 레코드를 사용하지만 DNS 호스트를 [도메인 연결](/office365/admin/get-help-with-domains/domain-connect)에서 사용할 수 있는 경우 **레코드 추가** 를 선택 합니다. **온라인 서비스 선택** 페이지에서 모든 기본값을 적용하고 **다음** 을 선택한 후 DNS 호스트의 페이지에서 **승인** 을 선택합니다.
    - 도메인 연결 사용이 설정되지 않은 다른 DNS 호스트에서 기존 DNS 레코드를 사용하는 경우 기존 서비스를 계속 연결할 수 있도록 DNS 레코드를 관리하는 것이 좋습니다. 자세한 내용은 [도메인 기본 사항](/office365/admin/get-help-with-domains/dns-basics)을 참조하세요.

2. 마법사의 단계를 따르면 전자 메일 및 기타 서비스가 설정됩니다.

    등록 프로세스가 완료되면 관리 센터로 이동하여 마법사를 따라 Office 앱을 설치하고 도메인을 추가하며 사용자를 추가하고 라이선스를 할당합니다. 초기 설정을 완료한 후 관리 센터의 **설정** 페이지를 사용하여 구독과 함께 제공되는 서비스를 계속 설정하고 구성할 수 있습니다.

    설정 마법사와 관리 센터 **설정** 페이지에 대한 자세한 내용은 [설정 마법사와 설정 페이지의 차이점](o365-setup-wizard-and-setup-page.md)을 참조하세요.

## <a name="finish-setting-up"></a>설정 완료

### <a name="set-up-outlook-for-email"></a>Outlook을 전자 메일로 설정

1. Windows 시작 메뉴에서 Outlook을 검색하고 선택합니다.

    (Mac을 사용하는 경우 도구 모음에서 Outlook을 열거나 Finder를 사용하여 Outlook을 찾습니다.)

    방금 Outlook을 설치한 경우 시작 페이지에서 **다음** 을 선택합니다.

2. **파일** \> **정보** \> **계정 추가** 를 선택합니다.

3. Microsoft 전자 메일 주소를 입력하고 **연결** 을 선택합니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/9fe86884-8a83-42cc-bca9-61a12e6dad31?autoplay=false]
  
[Outlook을 전자 메일로 설정](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f)에서 자세히 알아보세요.
  
### <a name="import-email"></a>전자 메일 가져오기

다른 이메일 계정으로 Outlook을 사용하는 경우 이전 전자 메일, 일정 및 연락처를 새 Microsoft 365 계정으로 가져올 수 있습니다.
  
1. **이전 전자 메일 내보내기**

    Outlook에서 **파일** \> **열기 &amp; 내보내기** \> **가져오기/내보내기** 를 선택합니다.

    **파일로 내보내기** 를 선택하고 다음 단계를 수행하여 Outlook 데이터 파일(.pst) 및 하위 폴더를 내보냅니다.

2. **이전 전자 메일 가져오기**

    Outlook에서 다시 **파일** \> **열기 &amp; 내보내기** \> **가져오기/내보내기** 를 선택합니다.

    이번에는 **다른 프로그램 또는 파일에서 가져 오기** 를 선택하고 다음 단계에 따라 이전 이메일을 내보낼 때 생성한 백업 파일을 가져옵니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/40f7df36-9e24-44e5-8791-e9ed0dd8fd21?autoplay=false]
  
[Outlook으로 전자 메일을 가져오기](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de)에서 자세히 알아보세요.

Exchange 관리 센터를 사용하여 모든 사용자의 전자 메일을 가져올 수도 있습니다. 자세한 내용은 [여러 전자 메일 계정을 마이그레이션하는 방법](/Exchange/mailbox-migration/mailbox-migration)을 참조하세요.
  
### <a name="use-a-public-website"></a>공용 웹 사이트 사용

Microsoft 365에는 비즈니스용 공용 웹 사이트가 포함되지 않습니다. 공용 웹 사이트를 설정하려면 GoDaddy 또는 WIX와 같은 Microsoft 파트너를 사용해 보세요.
  
1. 관리 센터에서 **리소스** 로 이동한 다음, **공용 웹 사이트** 를 선택합니다.

2. 옵션 중 하나에서 **자세한 정보** 를 선택한 다음, 웹 사이트 파트너에 등록하고 해당 도구를 사용하여 사이트를 설정하고 디자인합니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/4839abc6-9323-4cbf-a79d-2907235f9ebb]

## <a name="related-content"></a>관련 콘텐츠

[웹 사이트 만들기](../../business-video/create-web-site.md)(비디오)\
[비즈니스용 Microsoft 365](../../business-video/index.yml)(링크 페이지)
