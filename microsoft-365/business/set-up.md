---
title: Microsoft 365 Business 설정
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Microsoft 365 Business를 설정 하는 방법을 알아보세요.
ms.openlocfilehash: cd59570cbcb9b027780e160117b44be88770d6b9
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37575551"
---
# <a name="set-up-microsoft-365-business-in-the-setup-wizard"></a>설치 마법사에서 Microsoft 365 Business 설정

## <a name="add-your-domain-users-and-set-up-policies"></a>도메인, 사용자 및 정책 설정 추가

[![레이블-관리 센터가 변경 중 이며 aka.ms/aboutM365preview에서 자세한 내용을 확인할 수 있습니다.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Microsoft 365 Business를 구매 하는 경우 소유 하 고 있는 도메인을 사용 하거나 [등록](sign-up.md)중에 하나를 구입 하는 옵션이 있습니다.

- 등록할 때 새 도메인을 구매한 경우 도메인은 모두 설정 되며 이동 하 여 [사용자를 추가 하 고 라이선스를 할당할](#add-users-and-assign-licenses)수 있습니다.

### <a name="add-your-domain-to-personalize-sign-in"></a>로그인 개인 설정에 도메인 추가

1. 전역 관리자 자격 증명을 사용 하 여 [Microsoft 365 관리 센터](https://admin.microsoft.com) 에 로그인 합니다. 

2. **도메인 추가** 또는 **사용자 추가** 를 선택 하 여 마법사를 시작 합니다.
    > [!IMPORTANT]
    > 등록할 때 도메인을 구매한 경우에 **는 추가 도메인** 단계가 표시 되지 않습니다. 대신 [사용자 추가](#add-users-and-assign-licenses) 로 이동 합니다.

    ![설정으로 이동을 선택 합니다.](media/gotosetupinadmincenter.png)
    
3. 마법사에서 사용 하려는 도메인 이름 (예 contoso.com)을 입력 합니다.


    ![로그인 페이지를 개인 설정 합니다.](media/personalizesignin.png)

    
4. 마법사의 단계에 따라 도메인을 소유 하 고 있는지 확인 하는 [dns 호스팅 공급자 (Office 365)에 dns 레코드를 만듭니다](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) . 도메인 호스트를 알고 있는 경우에는 [호스트 관련 지침](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)도 참조 하세요.

    호스팅 공급자가 GoDaddy 이거나 [도메인 연결](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)을 사용 하 여 사용 하도록 설정 된 다른 호스트의 경우에는 프로세스가 쉬우며 자동으로 로그인 하 라는 메시지가 표시 되며 사용자가 대신 인증을 사용 하는 것이 좋습니다.

    ![GoDaddy 액세스 확인 페이지에서 권한 부여를 선택 합니다.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>사용자 추가 및 라이선스 할당

마법사에서 사용자를 추가할 수 있지만 나중에 관리 센터에서 [사용자를 추가할](add-users-m365b.md) 수도 있습니다. 또한 로컬 도메인 컨트롤러가 있는 경우 [AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)를 사용 하 여 사용자를 추가할 수 있습니다.

#### <a name="add-users-in-the-wizard"></a>마법사에서 사용자 추가

마법사에서 추가 하는 모든 사용자는 Microsoft 365 비즈니스 라이선스를 자동으로 할당 받습니다.

![마법사의 새 사용자 추가 페이지 스크린샷](media/addnewuserspage.png)

1. Microsoft 365 비즈니스 구독에 기존 사용자가 있는 경우 (예: Azure AD Connect를 사용한 경우) 지금 라이선스를 할당 하는 옵션이 제공 됩니다. 해당 사용자에게도 라이선스를 추가합니다.

2. 사용자를 추가한 후에는 추가한 새 사용자와 자격 증명을 공유 하는 옵션도 제공 됩니다. 자격 증명을 인쇄, 전자 메일로 전송 또는 다운로드할 수 있습니다.

3. 조직에 대 한 팀 만들기에서 팀을 추가 하 고 사용자를 추가 하도록 선택할 수 있습니다. 나중에이 작업을 수행할 수도 있습니다. 자세한 내용은 [회사 전체 팀 만들기](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3)를 참조 하세요.

4. 전자 메일 메시지 마이그레이션을 건너뛰고 **전자 메일 메시지 마이그레이션** 페이지에서 **다음**을 선택합니다. 

    다른 전자 메일 공급자에서 전환 중이 고 나중에 데이터를 복사 하려는 경우 [전자 메일 및 연락처를 Office 365로 마이그레이션할](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e)수 있습니다.


### <a name="connect-your-domain"></a>도메인 연결

> [!NOTE]
> . Onmicrosoft 도메인을 사용 하도록 선택한 경우 또는 Azure AD Connect를 사용 하 여 사용자를 설정 하는 경우에는이 단계가 표시 되지 않습니다.
  
서비스를 설정하려면 DNS 호스트 또는 도메인 등록 기관에서 레코드를 업데이트해야 합니다.
  
1. 설정 마법사는 일반적으로 사용자의 등록 기관을 감지하여 등록 기관 웹 사이트에서 NS 레코드를 업데이트하기 위한 단계별 지침의 링크를 제공합니다. 그렇지 [않은 경우 이름 서버를 변경 하 여 도메인 등록 기관에 Office 365을 설정](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)합니다. 

    - 기존 웹 사이트와 같이 기존 DNS 레코드가 있지만 DNS 호스트가 [도메인 연결](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)을 사용 하도록 설정 된 경우 **에는 레코드 추가**를 선택 합니다. **온라인 서비스 선택** 페이지에서 기본값을 모두 적용 하 고 **다음**을 선택한 다음, DNS 호스트의 페이지에서 **권한 부여** 를 선택 합니다.
    - 다른 DNS 호스트 (도메인 연결에 대해 사용 하도록 설정 되지 않음)의 기존 DNS 레코드가 있는 경우에는 자체 DNS 레코드를 관리 하 여 기존 서비스가 연결 된 상태 인지 확인할 수 있습니다. 자세한 내용은 [도메인 기본 사항을](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) 참조 하세요.

        ![도메인 연결 페이지에서 자체 DNS 레코드를 관리 합니다.](media/connectyourdomainpage.png)

2. 마법사의 단계를 따르고 전자 메일 및 기타 서비스가 설정 됩니다.

### <a name="protect-data-and-devices"></a>데이터 및 장치 보호 

마법사에서 설정한 정책이 *모든 사용자*라는 [보안 그룹](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) 에 자동으로 적용 됩니다. 관리 센터에서 정책을 할당 하는 추가 그룹을 만들 수도 있습니다.

1. **모바일 장치에서 작업 파일 보호** 옵션은 **장치를 분실 하거나 도난당 한 경우 기본적으로 작업 파일을 보호** 합니다. **사용자가 모바일 장치에서 Office 파일에 액세스 하는 방법 관리**를 설정 하는 옵션을 사용할 수 있으며,이는 권장 되는 방법입니다.

    ![모바일 장치에서 작업 파일 보호 페이지의 스크린샷](media/protectworkfilesondevices.png)

     - **장치를 분실 하거나 도난당** 하 여 [기본값](protect-work-files-on-lost-or-stolen-device.md)을 표시 하려면 작업 파일 보호를 확장 합니다.

        ![손실 된 장치에서 파일을 보호 하는 기본값의 스크린샷](media/protectworkfilesondevicesdefault.png)

    - **사용자가 모바일 장치에서 Office 파일에 액세스 하는 방법 관리** 를 선택 하 고 확장 하 여 [기본값](manage-user-access-on-mobile-devices.md)을 표시 합니다. 설치 중에 기본값을 사용 하 여 모든 사용자에 게 적용 되는 Android, iOS 및 Windows 10에 대 한 응용 프로그램 정책을 만드는 것이 좋습니다. 설치가 완료되면 추가로 정책을 만들 수 있습니다.

        ![휴대폰의 Office 파일에 대 한 보호 설정 스크린샷](media/useraccessonmobile.png)

2. 데이터 및 장치를 보호 하는 마지막 단계에서는 Windows 10 장치를 보호 하기 위한 정책을 설정할 수 있습니다. 사용자의 Windows 10이 조직에 연결할 때 이러한 설정이 자동으로 적용 됩니다. **보안 Windows 10 장치** 를 확장 하 여 [기본값](secure-windows-10-devices.md)을 보고 수정할 수 있습니다.
3. Windows 10 장치에 [Office를 자동으로 설치](install-office-on-windows-10-during-setup.md) 하도록 선택할 수도 있습니다.

    ![Set Windows 10 장치 구성 페이지의 스크린샷](media/setwin10config.png)


## <a name="deploy-office-365-client-apps"></a>Office 365 클라이언트 앱 배포

설정 중에 Office 앱을 자동으로 설치 하도록 선택한 경우 사용자가 자신의 회사 자격 증명을 사용 하 여 Windows 디바이스에서 Azure AD에 로그인 한 후에 앱이 Windows 10 장치에 설치 됩니다.
모바일 iOS 또는 Android 장치에 Office를 설치 하려면 [Set up 모바일 장치 For Microsoft 365 Business users](set-up-mobile-devices.md)를 참조 하세요.

Office를 개별적으로 설치할 수도 있습니다. 자세한 내용은 [PC 또는 Mac에 Office 설치](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) 를 참조 하세요.
