---
title: Id 및 장치를 구현 하기 위한 필수 구성 요소 작업 액세스 정책-Microsoft 365 Enterprise | Microsoft 문서
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
ms.openlocfilehash: e97b16b3520d500737e0b397e8e2a515ecac9b3f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870374"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Id 및 장치 액세스 정책을 구현 하기 위한 필수 구성 요소 작업

이 문서에서는 권장된 id 및 장치 액세스 정책을 배포할 수 있습니다를 구현 하는 데 필요한 필수 구성 요소에 설명 합니다. 사용자에 게 조건부 액세스를 위한 기술 필수를 최상의 SSO 환경을 제공 하는 것이 좋습니다 기본 플랫폼 클라이언트 구성에 설명 합니다.


## <a name="prerequisites"></a>필수 구성 요소

권장된 identity 및 장치 액세스 정책을 구현 하기 전에 조직에서 충족 해야 하는 몇가지 필수 구성 요소 있습니다. 사용자 환경에 적용 되는 필수 구성 요소에 대 한 다음 표를 참조 합니다. 


| 구성 | 클라우드만 | Active Directory 암호 해시 동기화 사용 |  AD FS와의 페더레이션 |
| :------------- | :-----------: | :--------------: | :------------: |
|  [암호 해시 동기화를 구성](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization)합니다. 이 누수 된 자격 증명을 검색 하는데 사용할 수 있어야 하 고 기반 조건부 액세스에서 위험에 대 한 작업을 수행할 수 있습니다. **참고:** 이것이 조직에서 관리 되는 인증을 통과 인증 (설명) 또는 연결 된 인증을 사용 하는 여부에 관계 없이 필요 합니다. |    | 예 | 예 |
| 회사 네트워크에 연결 된 통해 회사 장치에 공백 문자가 있는 경우에 사용자를 자동으로 로그인 [원활 하 게 single sign-on 설정](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) 합니다. |  | 예 |  |
| [Configure 라는 네트워크](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal)입니다. Azure AD Id 보호 수집 하 고 위험 점수를 생성 하려면 모든 사용 가능한 세션 데이터를 분석 합니다. 네트워크 구성 라는 Azure AD에 네트워크에 대 한 조직의 공용 IP 범위를 지정 하는 것이 좋습니다. 이러한 범위에서 들어오는 트래픽이 않으므로 기업 환경 외부에서 트래픽을 더 높은 위험 점수도 취급 됩니다 감소 위험 점수를 부여 됩니다. | 예  | 예 | 예 |
|[셀프서비스 암호 재설정 (SSPR) 및 다단계 인증 (MFA)에 대 한 모든 사용자를 등록](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged)합니다. 시간 보다 먼저 Azure MFA에 대 한 사용자를 등록 하는 것이 좋습니다. Azure AD Id 보호를 사용 하면 추가 보안 확인을 수행 하려면 Azure MFA를 활용 합니다. 또한 로그인 환경을 최적화에 대 한 것이 좋습니다 사용자 설치 [Microsoft 인증자 응용 프로그램](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) 및 해당 장치에서 Microsoft 회사 포털 응용 프로그램입니다. 이러한 각 플랫폼에 대 한 응용 프로그램 저장소에서 설치할 수 있습니다. | 예 | 예 | 예 |
| [도메이에 가입된 Windows 컴퓨터에 대해 자동 장치 등록 사용](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup). 조건부 액세스를 통해 서비스에 연결하는 장치가 도메인에 가입되거나 호환되는 장치가 되도록 할 수 있습니다. Windows 컴퓨터에서 이 기능을 지원하려면 Azure AD를 사용하여 장치를 등록해야 합니다.  이 문서에서는 자동 장치 등록을 구성하는 방법에 대해 설명합니다. |   | 예 |  예 |
| **사용자의 지원 팀 준비**. MFA를 완료할 수 없는 사용자에 대한 계획을 시행합니다. 이러한 사용자를 정책 제외 그룹에 추가하거나 이들에 대한 새 MFA 정보를 등록하면 됩니다. 이러한 보안에 중요한 변경을 하기 전에 실제 사용자가 요청을 하도록 해야 합니다. 사용자의 관리자에 대해 승인을 통해 도움을 주도록 요구하는 것이 효과적인 단계입니다. | 예 | 예 | 예 |
| [온-프레미스 AD에 대한 암호 쓰기 저장 구성](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started). 암호 쓰기 저장을 사용하여 Azure AD는 높은 계정 손상 위험이 검색된 경우 사용자가 자신의 온-프레미스 암호를 변경하도록 요구할 수 있습니다. Azure AD Connect를 둘 중의 한 가지 방법으로 사용하여 이 기능을 활성화할 수 있습니다. Azure AD Connect 설정 마법사의 선택적 기능 화면에서 암호 쓰기 저장을 사용하도록 설정하거나 Windows PowerShell을 통해 사용하도록 설정할 수 있습니다. |   | 예 | 예 |
| [Azure Active Directory Id 보호를 사용 하도록 설정](https://docs.microsoft.com/en-us/azure/active-directory/identity-protection/enable)합니다. Azure AD Id 보호를 사용 하면 조직의 id가 영향을 줄 수 있는 잠재적인 취약점 검색 및 낮음, 보통 및 높은 로그인 위험 및 사용자 위험에 자동된 업데이트 관리 정책을 구성할 수 있습니다.  | 예 | 예 | 예 |
| [비즈니스 온라인 용 Skype](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)및 [Exchange Online](https://support.office.com/article/Enable-or-disable-modern-authentication-in-Exchange-Online-58018196-f918-49cd-8238-56f57f38d662) 에 대 한 **최신 인증을 사용** 합니다. 현대 인증은 다단계 인증 (MFA)를 사용 하기 위한 필수 구성 요소입니다. 현대 인증이 Office 2016 클라이언트, SharePoint Online 및 비즈니스용 OneDrive에 대 한 기본적으로 사용 됩니다. | 예 | 예 | 예 |
|||||



## <a name="recommended-client-configurations"></a>권장되는 클라이언트 구성
이 섹션에서는 조건부 액세스에 대한 기술적인 필수 구성 요소뿐만 아니라 사용자에게 최상의 SSO 환경을 제공하기 위해 Microsoft에서 권장하는 기본 플랫폼 클라이언트 구성에 대해서도 설명합니다.

### <a name="windows-devices"></a>Windows 장치
Azure는 온-프레미스와 Azure AD에 대해 모두 가장 원활한 SSO 경험을 제공하도록 설계되었으므로 Windows 10(버전 1703 이상)을 사용하는 것이 좋습니다. 회사 또는 학교에서 발급한 장치는 Azure AD에 직접 가입하도록 구성하거나 조직이 온-프레미스 AD 도메인 가입을 사용하는 경우 해당 장치를 [Azure AD에 자동으로 등록하도록 구성](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)해야 합니다.

BYOD Windows 장치의 경우 사용자는 "회사 또는 학교 계정 추가"를 사용할 수 있습니다. 참고로 Windows 10의 Chrome 브라우저 사용자는 사용자가 Edge/IE와 같은 원활한 로그인 경험을 얻을 수 있도록 [확장 기능을 설치](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog)해야 합니다. 또한 조직이 도메인에 가입된 Windows 7 장치를 가지고 있는 경우 Azure AD에 장치를 등록하려면 Windows 10이 아닌 컴퓨터에 대해 Microsoft Workplace Join [패키지를 설치](https://www.microsoft.com/download/details.aspx?id=53554)할 수 있습니다.

### <a name="ios-devices"></a>iOS 장치
조건부 액세스 또는 MFA 정책을 배포 하기 전에 사용자 장치에서 [Microsoft 인증자 응용 프로그램](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) 을 설치 하는 것이 좋습니다. 사용자는 작업을 추가 하 여 Azure AD와 해당 장치를 등록 또는 학교 계정 하 라는 메시지가 나타나면 또는 Intune 회사 포털 응용 프로그램 관리에 해당 장치를 등록할 수를 설치할 때에 최소한 앱이 설치 해야 합니다. 이 구성 된 조건부 액세스 정책에 따라 달라 집니다.

### <a name="android-devices"></a>Android 장치
조건부 액세스 정책을 배포하기 전에 또는 특정 인증 시도 중에 요구하는 경우 사용자가 [Intune 회사 포털 앱](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en
) 및 [Microsoft Authenticator 앱](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)을 설치하는 것이 좋습니다. 앱 설치 후 사용자에게 Azure AD에 등록하거나 사용자의 장치를 Intune에 등록할 것을 요구할 수 있습니다. 이는 구성된 조건부 액세스 정책에 따라 달라집니다.

또한 Intune MDM 정책에 의해 메일 계정을 관리 및 보호할 수 있도록 회사 소유 장치(COD)를 Android for Work 또는 Samsung Knox를 지원하는 OEM 및 버전에 대해 표준화하는 것이 좋습니다.


### <a name="recommended-email-clients"></a>권장되는 메일 클라이언트
다음 전자 메일 클라이언트 현대 인증 및 조건부 액세스를 지원 합니다. 

|플랫폼|클라이언트|버전/참고|
|:-------|:-----|:------------|
|**Windows**|Outlook|2016, 2013 [최신 인증 사용](https://support.office.com/article/Enable-Modern-Authentication-for-Office-2013-on-Windows-devices-7dc1c01a-090f-4971-9677-f1b192d6c910), [필수 업데이트](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|iOS용 Outlook|[최신](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Android용 Outlook|[최신](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2016|
|**Linux**|지원되지 않음||
|||


### <a name="recommended-client-platforms-when-securing-documents"></a>문서를 보호할 때 권장되는 클라이언트 플랫폼
보안 문서 정책을 적용한 경우 다음 클라이언트를 권장합니다.

|플랫폼|Word/Excel/PowerPoint|OneNote|OneDrive 앱|SharePoint 앱|OneDrive 동기화 클라이언트|
|:-------|:-----|:------------|:-------|:-------------|:-----|
|Windows 7|지원됨|지원됨|해당 없음|해당 없음|미리 보기<sup>*</sup>|
|Windows 8.1|지원됨|지원됨|해당 없음|해당 없음|미리 보기<sup>*</sup>|
|Windows 10|지원됨|지원됨|해당 없음|해당 없음|미리 보기<sup>*</sup>|
|Windows Phone 10|지원되지 않음|지원되지 않음|지원되지 않음|지원되지 않음|지원되지 않음|
|Android|지원됨|지원|지원|지원됨|해당 없음|
|iOS|지원됨|지원|지원|지원됨|해당 없음|
|macOS|공개 미리 보기|공개 미리 보기|해당 없음|해당 없음|지원되지 않음|
|Linux|지원되지 않음|지원되지 않음|지원되지 않음|지원되지 않음|지원되지 않음|

<sup>*</sup>조건부 액세스를 사용 하 여 [OneDrive 동기화 클라이언트](https://support.office.com/article/Azure-Active-Directory-conditional-access-with-the-OneDrive-sync-client-on-Windows-028d73d7-4b86-4ee0-8fb7-9a209434b04e)와 함께 하는 방법에 대 한 자세한 내용은 합니다.

### <a name="office-365-client-support"></a>Office 365 클라이언트 지원
Office 365 클라이언트 지원에 대 한 자세한 내용은 다음 문서를 참조 하십시오.
- [Office 365 클라이언트 응용 프로그램 지원-조건부 액세스](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-conditional-access)
- [Office 365 클라이언트 응용 프로그램 지원-모바일 응용 프로그램 관리](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-mobile-application-management)
- [Office 365 클라이언트 응용 프로그램 지원-현대 인증](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-modern-authentication)

## <a name="protecting-administrator-accounts"></a>관리자 계정 보호
Azure Active Directory에는 미리 구성된 해 둔 조건부 액세스 정책에 대 한 관리자 액세스를 보호를 시작할 수 있는 간단한 방법을 제공 합니다. Azure AD 내에서 조건부 액세스 블레이드로 이동 하 고이 정책에 대 한 찾습니다- **기본 정책: 관리자의 MFA 필요**합니다. 이 정책에을 **즉시 정책을 사용 하 여**선택 합니다. 

이 정책은 다음 역할에 대 한 MFA 필요합니다.
- 전역 관리자
- SharePoint 관리자
- Exchange 관리자
- 조건부 액세스 관리자
- 보안 관리자

자세한 내용은 [Azure AD 관리 계정에 대 한 초기 보안 정책](https://cloudblogs.microsoft.com/enterprisemobility/2018/06/22/baseline-security-policy-for-azure-ad-admin-accounts-in-public-preview/)을 참조 하십시오.

추가 권장 사항은 다음과 같습니다.
- Azure AD 권한 있는 Id 관리를 사용 하 여 영구 관리 계정 수를 줄입니다. [P i M를 사용 하 여 시작](https://docs.microsoft.com/en-us/azure/active-directory/privileged-identity-management/pim-getting-started)을 참조 하십시오. 
- [Office 365에서 권한이 부여 된 액세스 관리를 사용 하 여](https://docs.microsoft.com/en-us/office365/securitycompliance/privileged-access-management-overview) 조직에서 기존를 사용할 수 있는 침해 보호 하기 위해 사용자는 관리자가 사용자 계정은 중요 한 데이터에 대 한 순위 액세스 또는 중요 한 구성 설정에 대 한 액세스 권한이 합니다. 
- Office 365 관리자 계정 관리에 대해서만 사용 합니다. 관리자가 정기적으로 비 관리 사용에 대 한 계정 하 고만 해당 직무와 관련 된 작업을 완료 하는데 필요한 경우에 관리 계정을 사용 하 여 별도 사용자가 있어야 합니다. [Office 365 관리자](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) 역할에는 Office 365 서비스에 대 한 더 많은 권한을 갖습니다.
- 이 [문서](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)에서 설명한 대로 Azure AD에서 권한이 부여 된 계정을 보호를 위한 모범 사례를 따릅니다.

## <a name="next-steps"></a>다음 단계

[일반적인 id 및 장치 액세스 정책 구성](identity-access-policies.md)

