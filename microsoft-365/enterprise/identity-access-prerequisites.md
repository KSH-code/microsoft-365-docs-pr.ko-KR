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
ms.openlocfilehash: ee517e774e0606c62efdc67d869ad0aca5a41640
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26870374"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Id 및 장치 액세스 정책을 구현 하기 위한 필수 구성 요소 작업

이 문서에서는 권장된 id 및 장치 액세스 정책을 배포 하려면 먼저 구현 하는 필수 구성 요소에 설명 합니다. 사용자에 게 조건부 액세스를 위한 기술 사전 요구 사항에 최상의 SSO 환경을 제공 하는 것이 좋습니다 기본 플랫폼 클라이언트 구성에 설명 합니다.


## <a name="prerequisites"></a>필수 구성 요소

권장된 identity 및 장치 액세스 정책을 구현 하기 전에 조직에서 충족 해야 하는 몇가지 필수 구성 요소 있습니다. 다음 표에서 사용자 환경에 적용 되는 필수 구성 요소에 자세히 설명 합니다. 


| 구성 | 클라우드만 | Active Directory 암호 해시 동기화 사용 |  경유 인증 |  AD FS와의 페더레이션 |
| :------------- | :-----------: | :--------------: | :------------: | :------------: |
|  [암호 해시 동기화를 구성](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization)합니다. 이 누수 자격 증명을 검색 하 고 위험 기반 조건부 액세스에 대 한에서 사용할 활성화 되어야 합니다. **참고:** 이것이 조직에서 관리 되는 인증을 통과 인증 (설명) 또는 연결 된 인증을 사용 하는 여부에 관계 없이 필요 합니다. |    | 예 | 예 | 예 |
| 회사 네트워크에 연결 된 통해 회사 장치에 공백 문자가 있는 경우에 사용자를 자동으로 로그인 [원활 하 게 single sign에서 사용 하도록 설정](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) 합니다. |  | 예 | 예 |  |
| [Configure 라는 네트워크](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal)입니다. Azure AD Id 보호 수집 하 고 위험 점수를 생성 하려면 모든 사용 가능한 세션 데이터를 분석 합니다. 네트워크 구성 라는 Azure AD에 네트워크에 대 한 조직의 공용 IP 범위를 지정 하는 것이 좋습니다. 이러한 범위에서 들어오는 트래픽이 감소 위험 점수가 부여 됩니다 및 기업 환경 외부에서 트래픽을 더 높은 위험 점수가 부여 됩니다. | 예  | 예 | 예 | 예 |
|[셀프서비스 암호 재설정 (SSPR) 및 다단계 인증 (MFA)에 대 한 모든 사용자를 등록](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged)합니다. 시간 보다 먼저 Azure MFA에 대 한 사용자를 등록 하는 것이 좋습니다. Azure AD Id 보호를 사용 하면 추가 보안 확인을 수행 하려면 Azure MFA를 활용 합니다. 또한 로그인 환경을 최적화에 대 한 것이 좋습니다 사용자 설치 [Microsoft 인증자 응용 프로그램](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) 및 해당 장치에서 Microsoft 회사 포털 응용 프로그램입니다. 이러한 각 플랫폼에 대 한 응용 프로그램 저장소에서 설치할 수 있습니다. | 예 | 예 | 예 | 예 |
| [도메인에 가입 된 Windows 컴퓨터의 자동 장치 등록을 사용 하도록 설정](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)합니다. 조건부 access 응용 프로그램을 연결 하는 장치는 도메인에 가입 또는 규격이 있는지 확인 합니다. 이 Windows 컴퓨터에 지원 하기 위해 Azure AD와 장치를 등록 합니다.  이 문서에서는 자동 장치 등록을 구성 하는 방법에 설명 합니다. |   | 예 |  예 |  예 |
| **Prepare 지원팀에 문의**합니다. MFA를 완료할 수 없는 사용자에 대 한 전체 요금제에 가입한 상태입니다. 이 정책 제외 그룹에 추가할 수 되거나 수 하 여 새 MFA 정보를 등록 합니다. 이러한 보안 관련 변경 작업 중 하나를 하기 전에 실제 사용자의 요청을 수행 하는 확인 해야 합니다. 사용자의 관리자 승인을 위해 필요한 효율적인 단계입니다. | 예 | 예 | 예 | 예 |  
| [Configure 암호 쓰기 저장을 온-프레미스 AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)합니다. 암호 쓰기 저장에는 사용자가 위험 가능성이 높은 계정 손상 감지 되 면 온-프레미스 암호를 변경 하려면 Azure AD 수 있습니다. Azure AD 연결을 사용 하 여 다음 두 방법 중 하나에서이 기능을 사용 하도록 설정할 수: Azure AD 연결 설치 마법사의 선택적 기능 화면에서 **암호 쓰기 저장** 을 사용 하거나 Windows PowerShell을 통해 사용 하도록 설정 합니다. |   | 예 | 예 | 예 |
| [Azure Active Directory Id 보호를 사용 하도록 설정](https://docs.microsoft.com/en-us/azure/active-directory/identity-protection/enable)합니다. Azure AD Id 보호를 사용 하면 조직의 id가 영향을 줄 수 있는 잠재적인 취약점 검색 및 낮음, 보통 및 높은 로그인 위험 및 사용자 위험에 자동된 업데이트 관리 정책을 구성할 수 있습니다.  | 예 | 예 | 예 | 예 |
| [비즈니스 온라인 용 Skype](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)및 [Exchange Online](https://support.office.com/article/Enable-or-disable-modern-authentication-in-Exchange-Online-58018196-f918-49cd-8238-56f57f38d662) 에 대 한 **최신 인증을 사용** 합니다. 현대 인증은 다단계 인증 (MFA)를 사용 하기 위한 필수 구성 요소입니다. 현대 인증이 Office 2016 클라이언트, SharePoint Online 및 비즈니스용 OneDrive에 대 한 기본적으로 사용 됩니다. | 예 | 예 | 예 | 예 |
||||||



## <a name="recommended-client-configurations"></a>권장되는 클라이언트 구성
이 섹션에서는 기본 플랫폼 클라이언트 구성으로 사용자에 게 조건부 액세스를 위한 기술 사전 요구 사항에 최상의 SSO 환경을 제공 하는 것이 좋습니다.

### <a name="windows-devices"></a>Windows 장치
Windows 10 (버전 1703 이상) 것이 좋습니다, 그리고 가장 자연 스러운 SSO 환경을 온-프레미스 및 Azure AD 모두를 위한 Azure 제공 하도록 설계 된 대로 합니다. 직접 Azure AD 참가 하도록 작업 또는 학교 발급 된 장치를 구성 해야 하거나 해당 장치를 [자동으로 구성 하 고 Azure AD를 자동으로 등록](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)해야 하는 경우 조직에서 사용 하 여 온-프레미스 AD 도메인 가입, 합니다.

BYOD Windows 장치에 대 한 사용자 **작업을 추가 또는 학교 계정을**사용할 수 있습니다. Note 동일한 원활 하 게 로그인 환경에서에 지/i E 사용자로 가져올 [확장을 설치](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) 하려면 Windows 10에서 Chrome 브라우저 사용자가 필요 합니다. 또한 조직에 도메인 가입 Windows 7 장치를 설치할 수 있습니다 Microsoft 직장 참가 [등록 패키지를 다운로드](https://www.microsoft.com/download/details.aspx?id=53554) 하는 Windows 10이 아닌 컴퓨터에 대 한 장치 Azure AD와 합니다.

### <a name="ios-devices"></a>iOS 장치
조건부 액세스 또는 MFA 정책을 배포 하기 전에 사용자 장치에서 [Microsoft 인증자 응용 프로그램](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) 을 설치 하는 것이 좋습니다. 사용자는 작업을 추가 하 여 Azure AD와 해당 장치를 등록 하는 메시지가 또는 계정, 학교 때 또는 Intune 회사 포털 응용 프로그램 관리에 해당 장치를 등록할 수를 설치할 때에 최소한 앱이 설치 해야 합니다. 이 구성 된 조건부 액세스 정책에 따라 달라 집니다.

### <a name="android-devices"></a>Android 장치
조건부 액세스 정책을 배포하기 전에 또는 특정 인증 시도 중에 요구하는 경우 사용자가 [Intune 회사 포털 앱](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) 및 [Microsoft Authenticator 앱](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)을 설치하는 것이 좋습니다. 앱 설치 후 사용자에게 Azure AD에 등록하거나 사용자의 장치를 Intune에 등록할 것을 요구할 수 있습니다. 이는 구성된 조건부 액세스 정책에 따라 달라집니다.

또한 회사 소유의 장치 (코드) Oem 및 Android 작업 또는 삼성 Knox 메일 계정을 허용, 관리 하 고 Intune MDM 정책에 의해 보호를 지 원하는 버전에서 표준화 하는 것이 좋습니다.


### <a name="recommended-email-clients"></a>권장되는 메일 클라이언트
다음 전자 메일 클라이언트 현대 인증 및 조건부 액세스를 지원 합니다. 

|플랫폼|클라이언트|버전/참고|
|:-------|:-----|:------------|
|**Windows**|Outlook|2016, 2013 [현대 인증을 사용 하도록 설정](https://support.office.com/article/Enable-Modern-Authentication-for-Office-2013-on-Windows-devices-7dc1c01a-090f-4971-9677-f1b192d6c910), [필수 업데이트](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|iOS용 Outlook|[최신](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Android용 Outlook|[최신](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2016|
|**Linux**|지원되지 않음||
|||


### <a name="recommended-client-platforms-when-securing-documents"></a>문서를 보호할 때 권장되는 클라이언트 플랫폼
보안 문서 정책이 적용 된 경우에 다음 클라이언트는 것이 좋습니다.

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

<sup>*</sup>[OneDrive 동기화 클라이언트](https://support.office.com/article/Azure-Active-Directory-conditional-access-with-the-OneDrive-sync-client-on-Windows-028d73d7-4b86-4ee0-8fb7-9a209434b04e)와 함께 조건부 액세스를 사용 하는 방법에 대 한 자세한 내용은 합니다.

### <a name="office-365-client-support"></a>Office 365 클라이언트 지원
Office 365 클라이언트 지원에 대 한 자세한 내용은 다음 문서를 참조 하십시오.
- [Office 365 클라이언트 응용 프로그램 지원-조건부 액세스](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-conditional-access)
- [Office 365 클라이언트 응용 프로그램 지원-모바일 응용 프로그램 관리](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-mobile-application-management)
- [Office 365 클라이언트 응용 프로그램 지원-현대 인증](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-modern-authentication)

## <a name="protecting-administrator-accounts"></a>관리자 계정 보호
Azure AD 미리 구성 된 조건부 액세스 정책에 대 한 관리자 액세스를 보호를 시작할 수 있는 간단한 방법을 제공 합니다. Azure AD에서 **조건부 액세스** 로 이동 하 고이 정책에 대 한 확인- **기본 정책: 관리자의 MFA 필요**합니다. 이 정책을 선택 하 고 **즉시 정책을 사용 하 여를**선택 합니다. 

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
- Office 365 관리자 계정 관리에 대해서만 사용 합니다. 관리자가 정기적으로 비 관리 사용에 대 한 계정 하 고만 해당 직무와 관련 된 작업을 완료 하는데 필요한 경우에 관리 계정을 사용 하 여 별도 사용자가 있어야 합니다. [Office 365 관리자](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) 역할에는 Office 365 서비스 보다 훨씬 더 많은 권한이 있습니다.
- 이 [문서](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)에서 설명한 대로 Azure AD에서 권한이 부여 된 계정을 보호를 위한 모범 사례를 따릅니다.

## <a name="next-steps"></a>다음 단계

[일반적인 id 및 장치 액세스 정책 구성](identity-access-policies.md)

