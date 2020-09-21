---
title: Id 및 장치 액세스 정책 구현에 대 한 작업-엔터프라이즈에 대 한 Microsoft 365 | Microsoft Docs
description: Id 및 장치 액세스 정책 및 구성을 구현 하기 전에 필요한 필수 구성 요소에 대해 설명 합니다.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/01/2020
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 5e6ea6adf30223d4750c2c38a6918482577b8d7f
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132027"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Id 및 장치 액세스 정책을 구현 하기 위한 필수 작업

이 문서에서는 권장 되는 id 및 장치 액세스 정책을 배포 하기 전에 구현 해야 하는 필수 구성 요소에 대해 설명 합니다. 이 문서에서는 또한 사용자에 게 최적의 SSO (single sign-on) 환경을 제공 하는 데 필요한 기본 플랫폼 클라이언트 구성과 조건부 액세스에 대 한 기술적 필수 구성 요소에 대해 설명 합니다.

## <a name="prerequisites"></a>필수 구성 요소

권장 되는 id 및 장치 액세스 정책을 구현 하기 전에 조직에서 Microsoft 365 및 Office 365에 대 한 이러한 id 및 인증 모델에 대해 충족 해야 하는 몇 가지 필수 구성 요소가 있습니다.

- 클라우드 전용
- 암호 해시 동기화 (PHS) 인증을 사용한 하이브리드
- 통과 인증을 통한 하이브리드 (PTA)
- 페더레이션된

다음 표에는 표시 된 경우를 제외 하 고 모든 id 모델에 적용 되는 필수 구성 요소 기능과 해당 구성이 자세히 나와 있습니다. 

| 구성 | 예외 |
| :------------- | :-----------: |
|  [PHS를 구성](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)합니다.  누수 된 자격 증명을 검색 하 고 위험 기반 조건부 액세스에 대해이를 수행 하려면이 옵션을 사용 하도록 설정 해야 합니다. **참고:** 조직에서 페더레이션 인증을 사용 하는지 여부에 관계 없이 필요 합니다. | 클라우드 전용 |
| [원활한 single sign-on을 사용](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) 하 여 조직 네트워크에 연결 된 조직 장치에 있을 때 사용자가 자동으로 로그인 하도록 합니다. | 클라우드 전용 및 페더레이션  |
| [명명된 네트워크 구성](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal). Azure AD ID 보호는 모든 사용 가능한 세션 데이터를 수집하고 분석하여 위험 점수를 생성합니다. 네트워크에 대 한 조직의 공용 IP 범위를 Azure AD 라는 네트워크 구성에서 지정 하는 것이 좋습니다. 이러한 범위에서 들어오는 트래픽에는 위험 점수가 절감 되 고 조직 환경 외부 로부터의 트래픽에는 위험 점수가 더 높은 것으로 지정 됩니다. | |
|[SSPR (셀프 서비스 암호 재설정) 및 MFA (multi-factor authentication)에 대 한 모든 사용자를 등록](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged)합니다. Azure Multi-factor Authentication을 위해 사용자에 게 미리 등록 하는 것이 좋습니다. Azure AD Id 보호는 Azure Multi-factor Authentication을 사용 하 여 추가 보안 확인을 수행 합니다. 또한 최상의 로그인 환경을 위해 사용자가 자신의 장치에 [Microsoft Authenticator 앱](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) 과 Microsoft 회사 포털 앱을 설치 하는 것이 좋습니다. 이러한 응용 프로그램은 각 플랫폼에 대해 앱 스토어에서 설치할 수 있습니다. | |
| [도메인에 가입 된 Windows 컴퓨터의 자동 장치 등록을 사용 하도록 설정](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)합니다. 조건부 액세스는 앱에 연결 하는 장치가 도메인에 가입 되었는지 또는 준수 되는지를 확인 합니다. Windows 컴퓨터에서 이 기능을 지원하려면 Azure AD를 사용하여 장치를 등록해야 합니다.  이 문서에서는 자동 장치 등록을 구성하는 방법에 대해 설명합니다. | 클라우드 전용 |
| **사용자의 지원 팀 준비**. MFA를 완료할 수 없는 사용자에 대한 계획을 시행합니다. 이를 정책 제외 그룹에 추가 하거나 새 MFA 정보를 등록할 수 있습니다. 이러한 보안 관련 변경 사항을 적용 하기 전에 실제 사용자가 요청을 수행 하 고 있는지 확인 해야 합니다. 사용자의 관리자에 대해 승인을 통해 도움을 주도록 요구하는 것이 효과적인 단계입니다. | |  
| [온-프레미스 AD에 대한 암호 쓰기 저장 구성](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started). 암호 쓰기 저장을 사용 하면 높은 위험 계정 손상 감지 시 사용자가 온-프레미스 암호를 변경 하도록 할 수 있습니다. Azure ad Connect 설치 마법사의 선택적 기능 화면에서 **암호 쓰기 저장** 을 사용 하도록 설정 하거나 Windows PowerShell을 통해 사용 하도록 설정 하 여 Azure ad connect를 사용 하 여이 기능을 사용 하도록 설정할 수 있습니다. | 클라우드 전용 |
| [AZURE AD 암호 보호를 구성](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)합니다. Azure AD 암호 보호는 알려진 약한 암호 및 해당 변종을 감지 및 차단 하며, 조직과 관련 된 추가 weak 용어를 차단할 수도 있습니다. 기본 전역 금지 암호 목록은 Azure AD 테 넌 트의 모든 사용자에 게 자동으로 적용 됩니다. 사용자 지정 금지 된 암호 목록에서 추가 항목을 정의할 수 있습니다. 사용자가 암호를 변경 하거나 다시 설정할 때 이러한 금지 된 암호 목록을 확인 하 여 강력한 암호를 사용 해야 합니다. |  |
| [Azure Active Directory Id 보호를 사용 하도록 설정](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)합니다. Azure AD Id 보호를 사용 하면 조직의 id에 영향을 미치는 잠재적인 취약점을 검색 하 고, 낮음, 보통 및 높음 로그인 위험 및 사용자 위험에 대 한 자동화 된 수정 정책을 구성할 수 있습니다.  | |
| [Exchange online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) 및 [비즈니스용 Skype online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)에 **최신 인증을 사용 하도록 설정** 합니다. 최신 인증은 MFA를 사용 하기 위한 필수 구성 요소입니다. Office 2016 및 2019 클라이언트, SharePoint 및 비즈니스용 OneDrive에 대 한 최신 인증은 기본적으로 사용 하도록 설정 되어 있습니다. |  |
|||

## <a name="recommended-client-configurations"></a>권장되는 클라이언트 구성
이 섹션에서는 사용자에 게 최상의 SSO 환경을 제공 하는 데 권장 되는 기본 플랫폼 클라이언트 구성 및 조건부 액세스에 대 한 기술적 필수 구성 요소에 대해 설명 합니다.

### <a name="windows-devices"></a>Windows 장치
Azure는 온-프레미스 및 Azure AD 둘 다에 사용할 수 있는 원활한 SSO 환경을 제공 하도록 디자인 되었기 때문에 Windows 10 (버전 2004 이상)이 권장 됩니다. 회사 또는 학교에서 발급 한 장치를 Azure AD에 직접 가입 하도록 구성 하거나, 조직에서 온-프레미스 AD 도메인 가입을 사용 하는 경우 해당 장치를 [자동으로 AZURE AD에 등록 하도록 구성](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)해야 합니다.

BYOD Windows 장치에서는 사용자가 **회사 또는 학교 계정 추가**를 사용할 수 있습니다. Windows 10 장치의 Google Chrome 브라우저 사용자는 Microsoft Edge 사용자와 동일한 순조로운 로그인 환경을 사용 하기 위해 [내선 번호를 설치](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) 해야 합니다. 또한 조직에서 도메인에 가입한 Windows 8 또는 8.1 장치를 사용 하는 경우 비 Windows 10 컴퓨터에 대해 Microsoft 작업 영역 참가를 설치할 수 있습니다. Azure AD를 사용 하 여 장치를 [등록 하는 패키지를 다운로드](https://www.microsoft.com/download/details.aspx?id=53554) 합니다.

### <a name="ios-devices"></a>iOS 장치
조건부 액세스 또는 MFA 정책을 배포 하기 전에 사용자 장치에 [Microsoft Authenticator 앱](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) 을 설치 하는 것이 좋습니다. 사용자가 회사 또는 학교 계정을 추가 하 여 Azure AD에 장치를 등록 해야 하거나, 관리자에 게 장치를 등록 하기 위해 Intune 회사 포털 앱을 설치할 때 앱이 설치 되어 있어야 합니다. 이는 구성 된 조건부 액세스 정책에 따라 달라 집니다.

### <a name="android-devices"></a>Android 장치
조건부 액세스 정책이 배포 되기 전이나 특정 인증 시도 중에 필요한 경우에는 사용자가 [Intune 회사 포털 앱](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) 및 [Microsoft Authenticator 앱](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) 을 설치 하는 것이 좋습니다. 앱 설치 후 사용자에게 Azure AD에 등록하거나 사용자의 장치를 Intune에 등록할 것을 요구할 수 있습니다. 이는 구성 된 조건부 액세스 정책에 따라 달라 집니다.

또한 조직 소유 장치는 Oem 및 회사에서 사용 하는 MDM 및 메일 계정을 허용 하기 위해 삼성 Knox를 지 원하는 버전에서 표준화 된 것으로 구성 하는 것이 좋습니다.


### <a name="recommended-email-clients"></a>권장되는 메일 클라이언트
다음 전자 메일 클라이언트는 최신 인증 및 조건부 액세스를 지원 합니다. 

|플랫폼|클라이언트|버전/참고|
|:-------|:-----|:------------|
|**Windows**|Outlook|2019, 2016, 2013 <BR> [최신 인증](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication), [필수 업데이트](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213) 사용|
|**iOS**|iOS용 Outlook|[최신](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Android용 Outlook|[최신](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2019 및 2016|
|**Linux**|지원되지 않음||
|||

### <a name="recommended-client-platforms-when-securing-documents"></a>문서를 보호할 때 권장되는 클라이언트 플랫폼

보안 문서 정책을 적용 한 경우 다음 클라이언트를 권장 합니다.

|플랫폼|Word/Excel/PowerPoint|OneNote|OneDrive 앱|SharePoint 앱|[OneDrive 동기화 클라이언트](https://docs.microsoft.com/onedrive/enable-conditional-access)|
|:-------|:-----|:------------|:-------|:-------------|:-----|
|Windows 8.1|지원|지원|해당 없음|해당 없음|지원|
|Windows 10|지원|지원|해당 없음|해당 없음|지원|
|Android|지원|지원|지원|지원|해당 없음|
|iOS|지원|지원|지원|지원|해당 없음|
|macOS|지원|지원|해당 없음|해당 없음|지원되지 않음|
|Linux|지원되지 않음|지원되지 않음|지원되지 않음|지원되지 않음|지원되지 않음|

### <a name="microsoft-365-client-support"></a>Microsoft 365 클라이언트 지원

Microsoft 365의 클라이언트 지원에 대 한 자세한 내용은 다음 문서를 참조 하십시오.

- [Microsoft 365 클라이언트 앱 지원-조건부 액세스](microsoft-365-client-support-conditional-access.md)
- [Microsoft 365 클라이언트 앱 지원-최신 인증](microsoft-365-client-support-modern-authentication.md)

## <a name="protecting-administrator-accounts"></a>관리자 계정 보호

Microsoft 365 E3 또는 E5 또는 별도의 Azure AD Premium P1 또는 P2 라이선스를 사용 하는 경우, 수동으로 만든 조건부 액세스 정책을 사용 하는 관리자 계정에 대해 MFA를 요구할 수 있습니다. 자세한 내용은 [조건부 액세스: 관리자를 위해 MFA 필요](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) 를 참조 하세요.

조건부 액세스를 지원 하지 않는 Microsoft 365 또는 Office 365 버전의 경우 [보안 기본값](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) 을 사용 하도록 설정 하 여 모든 계정에 대해 MFA를 요구할 수 있습니다.

몇 가지 추가 권장 사항은 다음과 같습니다.

- [AZURE AD 권한을 가진 Id 관리](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-getting-started) 를 사용 하 여 영구 관리 계정의 수를 줄입니다. 
- [권한이 부여 된 액세스 관리를 사용](../compliance/privileged-access-management-overview.md) 하 여 중요 한 데이터에 대 한 액세스 또는 중요 한 구성 설정에 대 한 액세스 권한이 있는 기존 권한 관리 계정을 사용 하는 위반 으로부터 조직을 보호할 수 있습니다. 
- *관리를 위해* [Microsoft 365 관리자 역할만](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) 할당 된 별도의 계정을 만들고 사용 합니다. 관리자는 일반 비 관리 사용을 위한 고유한 사용자 계정을 가져야 하며, 역할 또는 작업 기능과 관련 된 작업을 완료 하는 데 필요한 경우에만 관리 계정을 사용 해야 합니다. 
- Azure AD에서 권한 있는 계정 보안을 위한 모범 [사례](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) 를 따릅니다.

## <a name="next-step"></a>다음 단계

[![2 단계: 일반 id 구성 및 조건부 액세스 정책 액세스](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-2.png)](identity-access-policies.md)

[일반 id 및 장치 액세스 정책 구성](identity-access-policies.md)
