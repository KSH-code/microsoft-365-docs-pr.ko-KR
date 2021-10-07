---
title: Microsoft 365 Business Premium 설정
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
- Adm_TOC
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: 도메인 및 사용자 추가, Microsoft 365 Business Premium 정책 설정 등을 포함하여 사용자 지정에 대한 설정 단계를 검색합니다.
ms.openlocfilehash: 9c2c9da3e9427f77f067001c5f244e7c6d4e247f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60196204"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a>설치 Microsoft 365 Business Premium 설정

## <a name="watch-overview-of-microsoft-365-setup"></a>시청: 설치 Microsoft 365 개요

설치에 대한 개요를 확인하려면 이 Microsoft 365 Business Premium 시청하세요.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

## <a name="add-your-domain-users-and-set-up-policies"></a>도메인, 사용자 추가 및 정책 설정

구매 Microsoft 365 Business Premium 소유한 도메인을 사용하거나 등록하는 동안 도메인을 구입할 [수 있습니다.](../../business-video/sign-up.md)

- 등록할 때 새 도메인을 구입하면 도메인이 모두 설정되어 [사용자 추가 및 라이선스를 할당](#add-users-and-assign-licenses)으로 이동할 수 있습니다.

### <a name="add-your-domain-to-personalize-sign-in"></a>로그인 개인 설정을 위한 도메인 추가

1. 전역 관리자 자격 증명을 사용하여 [Microsoft 365 관리 센터](https://admin.microsoft.com)에 로그인합니다. 

2. **설정으로 이동** 을 선택해 마법사를 시작합니다.

    ![설정으로 이동을 선택합니다.](../../media/gotosetupinadmincenter.png)

3. **Office 앱 설치** 페이지에서 컴퓨터에 선택적으로 앱을 설치할 수 있습니다.
    
4. **도메인 추가** 단계에서 사용할 도메인 이름(예: contoso.com)을 입력합니다.

    > [!IMPORTANT]
    > 등록할 때 도메인을 구입한 경우에는 **도메인 추가** 단계가 표시되지 않습니다. 대신 [사용자 추가](#add-users-and-assign-licenses)로 이동하세요.

    ![Screenshot of the Personalize your sign-in page.](../../media/adddomain.png)

    
4. 마법사의 단계에 따라 도메인을 소유하고 Microsoft 365 DNS 호스팅 공급자에서 [DNS](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) 레코드 만들기를 수행합니다. 도메인 호스트를 알고 있는 경우 [Microsoft 365에 도메인 추가](/microsoft-365/admin/setup/add-domain)도 참조하세요.

    호스팅 공급자가 GoDaddy이거나 [도메인 연결](/office365/admin/get-help-with-domains/domain-connect)을 사용하는 다른 호스트를 사용하는 경우에는 프로세스가 간단하며, 자동으로 로그인하라는 메시지가 표시되고 Microsoft가 사용자를 대신하여 인증하도록 합니다.

    ![GoDaddy 액세스 확인 페이지에서 승인을 선택합니다.](../../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>사용자 추가 및 라이선스 할당

마법사에서 사용자를 추가하거나 관리 센터에서 [나중에 사용자를 추가](../add-users/add-users.md)할 수도 있습니다. 또한 로컬 도메인 컨트롤러를 사용하는 경우 [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express)를 사용하여 사용자를 추가할 수 있습니다.

#### <a name="add-users-in-the-wizard"></a>마법사에서 사용자 추가

마법사에서 추가하는 모든 사용자에게 자동으로 라이선스가 Microsoft 365 Business Premium.

![Screenshot of the Add new users page in the wizard.](../../media/addnewuserspage.png)

1. Microsoft 365 Business Premium 구독에 기존 사용자가 있는 경우(예: Azure AD 커넥트 사용하는 경우) 라이선스를 사용자에게 지금 할당할 수 있는 옵션이 제공됩니다. 해당 사용자에게도 라이선스를 추가합니다.

2. 사용자를 추가한 후에는 새로 추가한 사용자와 자격 증명을 공유하는 옵션도 여기에 표시됩니다. 자격 증명을 인쇄, 전자 메일로 전송 또는 다운로드할 수 있습니다.

### <a name="connect-your-domain"></a>도메인 연결

> [!NOTE]
> .onmicrosoft 도메인을 사용하거나 Azure AD Connect를 사용하여 사용자를 설정하는 경우에는 이 단계가 표시되지 않습니다.
  
서비스를 설정하려면 DNS 호스트 또는 도메인 등록 기관에서 레코드를 업데이트해야 합니다.
  
1. 설정 마법사는 일반적으로 사용자의 등록 기관을 감지하여 등록 기관 웹 사이트에서 NS 레코드를 업데이트하기 위한 단계별 지침의 링크를 제공합니다. 그렇지 않은 경우 도메인 등록 기관에서 이름 Microsoft 365 [변경합니다.](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md) 

    - 기존 웹 사이트와 같은 기존 DNS 레코드를 사용하지만 DNS 호스트를 [도메인 연결](/office365/admin/get-help-with-domains/domain-connect)에서 사용할 수 있는 경우 **레코드 추가** 를 선택 합니다. **온라인 서비스 선택** 페이지에서 모든 기본값을 적용하고 **다음** 을 선택한 후 DNS 호스트의 페이지에서 **승인** 을 선택합니다.
    - 도메인 연결 사용이 설정되지 않은 다른 DNS 호스트에서 기존 DNS 레코드를 사용하는 경우 기존 서비스를 계속 연결할 수 있도록 DNS 레코드를 관리하는 것이 좋습니다. 자세한 내용은 [도메인 기본 사항](/office365/admin/get-help-with-domains/dns-basics)을 참조하세요.

        ![레코드 활성화 페이지.](../../media/activaterecords.png)

2. 마법사의 단계를 따르면 전자 메일 및 기타 서비스가 설정됩니다.

### <a name="protect-your-organization"></a>조직 보호 

마법사에서 설정한 정책은 모든 사용자라는 [보안](/office365/admin/create-groups/compare-groups#security-groups) 그룹에 *자동으로 적용됩니다.* 추가 그룹을 만들어 관리 센터에서 정책을 할당할 수도 있습니다.

1. 고급 사이버 위협으로부터 보호 강화에서 Advanced [Threat Protection이](../../security/office-365-security/defender-for-office-365.md) 앱의 파일 및 링크를 Office 365 수 있는 기본값을 Office 좋습니다.

    ![보호 강화 페이지의 스크린샷.](../../media/increasetreatprotection.png)


2. 중요한  데이터 누출 방지 페이지에서 기본값을 수락하여 Office 365 DLP(데이터 손실 방지)를 설정하여 Office 앱에서 중요한 데이터를 추적하고 조직 외부에서 이러한 데이터를 실수로 공유하지 못하게 합니다.

3. 모바일용 Office 데이터 보호 **페이지에서** 모바일 앱 관리를 그대로 두고 설정을 확장하고 검토한 다음 모바일 앱 관리 정책 **만들기를 선택합니다.**

    ![Screenshot of Protect data in Office for mobile page.](../../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a>Windows 10 PC 보안

왼쪽 검색 창에서  설치를 선택한 다음 로그인 및 보안에서 보안 컴퓨터 **Windows 10 선택합니다.** **보기를** 선택하면 시작됩니다. 자세한 [지침은 Windows 10 컴퓨터](secure-win-10-pcs.md) 보안을 참조하세요.

## <a name="deploy-office-365-client-apps"></a>클라이언트 Office 365 앱 배포

설치 중에 Office 앱을 자동으로 설치하도록 선택한 경우 사용자가 Windows 장치에서 Azure AD에 로그인한 후 앱은 Windows 10 장치에 설치됩니다.

모바일 iOS Office 장치에 설치하려면 사용자용 모바일 장치 [Microsoft 365 Business Premium 참조합니다.](set-up-mobile-devices.md)

또한 개별적으로 설치 Office 수 있습니다. 지침은 Office PC 또는 [Mac에](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) 설치를 참조하세요.

## <a name="related-content"></a>관련 콘텐츠

[Microsoft 365 Business 교육 비디오](../../business-video/index.yml)(링크 페이지)
