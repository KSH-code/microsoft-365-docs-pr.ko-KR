---
title: Id 및 장치 액세스 정책을 구현 하기 위한 필수 작업-Microsoft 365 Enterprise | Microsoft Docs
description: ID 및 장치 액세스 정책과 구성을 적용하는 방법에 관한 Microsoft 권장 정책을 설명합니다.
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 8ac644ccd7772d8e4c53395c8a42ff6ddbd683a6
ms.sourcegitcommit: a6878de8ab977b675a45fc847ff46a9c0365dc56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2019
ms.locfileid: "35231861"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Id 및 장치 액세스 정책을 구현 하기 위한 필수 작업

이 문서에서는 권장 되는 id 및 장치 액세스 정책을 배포 하기 전에 구현 해야 하는 필수 구성 요소에 대해 설명 합니다. 이 문서에서는 또한 사용자에 게 최상의 SSO 환경을 제공 하는 데 권장 되는 기본 플랫폼 클라이언트 구성과 조건부 액세스에 대 한 기술적 필수 구성 요소에 대해 설명 합니다.


## <a name="prerequisites"></a>필수 구성 요소

권장 되는 id 및 장치 액세스 정책을 구현 하기 전에 조직에서 충족 해야 하는 몇 가지 필수 구성 요소가 있습니다. 다음 표에서는 사용자 환경에 적용 되는 필수 구성 요소에 대해 자세히 설명 합니다. 


| 구성 | 클라우드만 | 암호 해시 동기화를 사용 하는 Active Directory |  통과 인증 |  AD FS와의 페더레이션 |
| :------------- | :-----------: | :--------------: | :------------: | :------------: |
|  [암호 해시 동기화를 구성](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization)합니다. 누수 된 자격 증명을 검색 하 고 위험 기반 조건부 액세스에 대해이를 수행 하려면이 옵션을 사용 하도록 설정 해야 합니다. **참고:** 조직이 통과 인증 (PTA) 또는 페더레이션 인증과 같은 관리 되는 인증을 사용 하는지 여부에 관계 없이이 단계를 수행 해야 합니다. |    | 예 | 예 | 예 |
| 회사 네트워크에 연결 된 회사 장치에 있을 때 사용자가 자동으로 로그인 하도록 하려면 [원활한 single sign-on을 사용 하도록 설정](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) 합니다. |  | 예 | 예 |  |
| [명명된 네트워크 구성](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal). Azure AD ID 보호는 모든 사용 가능한 세션 데이터를 수집하고 분석하여 위험 점수를 생성합니다. 네트워크에 대 한 조직의 공용 IP 범위를 Azure AD 라는 네트워크 구성에서 지정 하는 것이 좋습니다. 이러한 범위에서 들어오는 트래픽에는 위험 점수가 감소 하 고 회사 환경 외부 로부터의 트래픽에 위험 점수가 더 높은 것으로 지정 됩니다. | 예  | 예 | 예 | 예 |
|[SSPR (셀프 서비스 암호 재설정) 및 MFA (multi-factor authentication)에 대 한 모든 사용자를 등록](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged)합니다. 사용자를 나중에 Azure MFA에 등록 하는 것이 좋습니다. Azure AD ID 보호에서는 Azure MFA를 사용하여 추가 보안 확인을 수행하도록 합니다. 또한 최상의 로그인 환경을 위해 사용자가 자신의 장치에 [Microsoft Authenticator 앱](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) 과 Microsoft 회사 포털 앱을 설치 하는 것이 좋습니다. 이러한 응용 프로그램은 각 플랫폼에 대해 앱 스토어에서 설치할 수 있습니다. | 예 | 예 | 예 | 예 |
| [도메인에 가입 된 Windows 컴퓨터의 자동 장치 등록을 사용 하도록 설정](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)합니다. 조건부 액세스는 앱에 연결 하는 장치가 도메인에 가입 되었는지 또는 준수 되는지를 확인 합니다. Windows 컴퓨터에서 이 기능을 지원하려면 Azure AD를 사용하여 장치를 등록해야 합니다.  이 문서에서는 자동 장치 등록을 구성하는 방법에 대해 설명합니다. |   | 예 |  예 |  예 |
| **사용자의 지원 팀 준비**. MFA를 완료할 수 없는 사용자에 대한 계획을 시행합니다. 이를 정책 제외 그룹에 추가 하거나 새 MFA 정보를 등록할 수 있습니다. 이러한 보안 관련 변경 사항을 적용 하기 전에 실제 사용자가 요청을 수행 하 고 있는지 확인 해야 합니다. 사용자의 관리자에 대해 승인을 통해 도움을 주도록 요구하는 것이 효과적인 단계입니다. | 예 | 예 | 예 | 예 |  
| [온-프레미스 AD에 대한 암호 쓰기 저장 구성](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started). 암호 쓰기 저장을 사용 하면 높은 위험 계정 손상 감지 시 사용자가 온-프레미스 암호를 변경 하도록 할 수 있습니다. Azure ad Connect 설치 마법사의 선택적 기능 화면에서 **암호 쓰기 저장** 을 사용 하도록 설정 하거나 Windows PowerShell을 통해 사용 하도록 설정 하 여 Azure ad connect를 사용 하 여이 기능을 사용 하도록 설정할 수 있습니다. |   | 예 | 예 | 예 |
| [Azure Active Directory Id 보호를 사용 하도록 설정](https://docs.microsoft.com/en-us/azure/active-directory/identity-protection/enable)합니다. Azure AD Id 보호를 사용 하면 조직의 id에 영향을 미치는 잠재적인 취약점을 검색 하 고, 낮음, 보통 및 높음 로그인 위험 및 사용자 위험에 대 한 자동화 된 수정 정책을 구성할 수 있습니다.  | 예 | 예 | 예 | 예 |
| [Exchange online](https://support.office.com/article/Enable-or-disable-modern-authentication-in-Exchange-Online-58018196-f918-49cd-8238-56f57f38d662) 및 [비즈니스용 Skype online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)에 **최신 인증을 사용 하도록 설정** 합니다. 최신 인증은 MFA (multi-factor authentication)를 사용 하기 위한 필수 구성 요소입니다. 최신 인증은 Office 2016 클라이언트, SharePoint Online 및 비즈니스용 OneDrive에 기본적으로 사용 하도록 설정 되어 있습니다. | 예 | 예 | 예 | 예 |
||||||



## <a name="recommended-client-configurations"></a>권장되는 클라이언트 구성
이 섹션에서는 사용자에 게 최상의 SSO 환경을 제공 하는 데 권장 되는 기본 플랫폼 클라이언트 구성 및 조건부 액세스에 대 한 기술적 필수 구성 요소에 대해 설명 합니다.

### <a name="windows-devices"></a>Windows 장치
Azure는 온-프레미스와 Azure AD에 대해 모두 가장 원활한 SSO 경험을 제공하도록 설계되었으므로 Windows 10(버전 1703 이상)을 사용하는 것이 좋습니다. 회사 또는 학교에서 발급 한 장치를 Azure AD에 직접 가입 하도록 구성 하거나, 조직에서 온-프레미스 AD 도메인 가입을 사용 하는 경우 해당 장치를 [자동으로 AZURE AD에 등록 하도록 구성](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)해야 합니다.

BYOD Windows 장치에서는 사용자가 **회사 또는 학교 계정 추가**를 사용할 수 있습니다. Windows 10의 Chrome-browser 사용자는 Edge/IE 사용자와 동일한 순조로운 로그인 환경을 가져오기 위해 [내선 번호를 설치](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) 해야 합니다. 또한 조직에서 도메인에 가입한 Windows 7 장치를 사용 하는 경우 비 Windows 10 컴퓨터에 대해 Microsoft 작업 영역 가입을 설치 하 여 Azure AD로 장치를 [등록 하는 패키지를 다운로드할](https://www.microsoft.com/download/details.aspx?id=53554) 수 있습니다.

### <a name="ios-devices"></a>iOS 장치
조건부 액세스 또는 MFA 정책을 배포하기 전에 사용자 장치에 [Microsoft Authenticator 앱](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)을 설치하는 것이 좋습니다. 사용자가 회사 또는 학교 계정을 추가 하 여 Azure AD에 장치를 등록 해야 하거나, 관리자에 게 장치를 등록 하기 위해 Intune 회사 포털 앱을 설치할 때 앱이 설치 되어 있어야 합니다. 이는 구성된 조건부 액세스 정책에 따라 달라집니다.

### <a name="android-devices"></a>Android 장치
조건부 액세스 정책을 배포하기 전에 또는 특정 인증 시도 중에 요구하는 경우 사용자가 [Intune 회사 포털 앱](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) 및 [Microsoft Authenticator 앱](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)을 설치하는 것이 좋습니다. 앱 설치 후 사용자에게 Azure AD에 등록하거나 사용자의 장치를 Intune에 등록할 것을 요구할 수 있습니다. 이는 구성된 조건부 액세스 정책에 따라 달라집니다.

또한 COD (회사 소유 장치)는 Oem 및 작업을 지 원하는 Android 및 메일 계정을 허용 하기 위한 Samsung Knox, Intune MDM 정책으로 관리 및 보호 되는 버전을 표준화 하는 것이 좋습니다.


### <a name="recommended-email-clients"></a>권장되는 메일 클라이언트
다음 전자 메일 클라이언트는 최신 인증 및 조건부 액세스를 지원 합니다. 

|플랫폼|클라이언트|버전/참고|
|:-------|:-----|:------------|
|**Windows**|Outlook|2016, 2013 [최신 인증 사용](https://support.office.com/article/Enable-Modern-Authentication-for-Office-2013-on-Windows-devices-7dc1c01a-090f-4971-9677-f1b192d6c910), [필수 업데이트](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|iOS용 Outlook|[최신](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Android용 Outlook|[최신](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2016|
|**Linux**|지원되지 않음||
|||


### <a name="recommended-client-platforms-when-securing-documents"></a>문서를 보호할 때 권장되는 클라이언트 플랫폼
보안 문서 정책을 적용 한 경우 다음 클라이언트를 권장 합니다.

|플랫폼|Word/Excel/PowerPoint|OneNote|OneDrive 앱|SharePoint 앱|OneDrive 동기화 클라이언트|
|:-------|:-----|:------------|:-------|:-------------|:-----|
|Windows 7|지원|지원|해당 없음|해당 없음|미리 보기<sup>*</sup>|
|Windows 8.1|지원|지원|해당 없음|해당 없음|미리 보기<sup>*</sup>|
|Windows 10|지원|지원|해당 없음|해당 없음|미리 보기<sup>*</sup>|
|Windows Phone 10|지원되지 않음|지원되지 않음|미지원|미지원|미지원|
|Android|지원|지원|지원|지원|해당 없음|
|iOS|지원|지원|지원|지원|해당 없음|
|macOS|공개 미리 보기|공개 미리 보기|해당 없음|해당 없음|지원되지 않음|
|Linux|지원되지 않음|지원되지 않음|지원되지 않음|지원되지 않음|지원되지 않음|

<sup>*</sup>자세한 내용은 [OneDrive 동기화 클라이언트](https://support.office.com/article/Azure-Active-Directory-conditional-access-with-the-OneDrive-sync-client-on-Windows-028d73d7-4b86-4ee0-8fb7-9a209434b04e)에서 조건부 액세스 사용을 참고 하세요.

### <a name="office-365-client-support"></a>Office 365 클라이언트 지원
Office 365 클라이언트 지원에 대 한 자세한 내용은 다음 문서를 참조 하십시오.
- [Office 365 클라이언트 앱 지원-조건부 액세스](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-conditional-access)
- [Office 365 클라이언트 앱 지원-모바일 응용 프로그램 관리](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-mobile-application-management)
- [Office 365 클라이언트 앱 지원-최신 인증](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-modern-authentication)

## <a name="protecting-administrator-accounts"></a>관리자 계정 보호
Azure AD는 미리 구성 된 조건부 액세스 정책을 사용 하 여 관리자 액세스를 간단 하 게 보호할 수 있는 방법을 제공 합니다. Azure AD에서 **조건부 액세스** 로 이동 하 여이 정책 ( **기본 정책: 관리자에 게 MFA 필요 (미리 보기))** 을 확인 합니다. 이 정책을 선택 하 고 **정책 즉시 사용**을 선택 합니다. 

이 정책에는 다음 역할에 대 한 MFA가 필요 합니다.
- 전역 관리자
- SharePoint 관리자
- Exchange 관리자
- 조건부 액세스 관리자
- 보안 관리자

자세한 내용은 [AZURE AD 관리자 계정에 대 한 기준 보안 정책](https://cloudblogs.microsoft.com/enterprisemobility/2018/06/22/baseline-security-policy-for-azure-ad-admin-accounts-in-public-preview/)를 참조 하세요.

추가 권장 사항은 다음과 같습니다.
- Azure AD Privileged Identity Management를 사용하여 영구 관리 계정 수를 줄입니다. [PIM 사용 시작](https://docs.microsoft.com/en-us/azure/active-directory/privileged-identity-management/pim-getting-started)을 참조 하세요. 
- [Office 365의 권한이 부여 된 액세스 관리를 사용](https://docs.microsoft.com/en-us/office365/securitycompliance/privileged-access-management-overview) 하 여 중요 한 데이터에 대 한 액세스 권한이 나 중요 한 구성 설정에 대 한 액세스 권한이 있는 기존 권한 관리 계정을 사용 하는 위반 으로부터 조직을 보호할 수 있습니다. 
- 관리에만 관리자 계정을 사용 합니다. 관리자는 일반 비 관리 사용을 위한 별도의 사용자 계정을 가져야 하며, 해당 작업 기능과 관련 된 작업을 완료 하는 데 필요한 경우에만 해당 관리자 계정을 사용 해야 합니다. [Office 365 관리자](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) 역할은 office 365 서비스 보다 훨씬 더 많은 권한을 가집니다.
- 이 [문서](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)에 설명 된 대로 Azure AD에서 권한 있는 계정 보안을 위한 모범 사례를 따릅니다.

## <a name="next-steps"></a>다음 단계

[일반 id 및 장치 액세스 정책 구성](identity-access-policies.md)

