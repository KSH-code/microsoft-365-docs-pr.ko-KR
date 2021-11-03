---
title: ID 및 장치 액세스 정책을 구현하기 위한 선행 작업 - 엔터프라이즈 Microsoft 365 위한 | Microsoft Docs
description: 이 문서에서는 ID 및 장치 액세스 정책 및 구성을 사용하기 위해 충족해야 하는 선행 요구 사항을 설명합니다.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: ba6a12036d6d6e0b53b930e2b1683781a474d186
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60666725"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>ID 및 장치 액세스 정책 구현을 위한 선행 작업

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- Azure

이 문서에서는 관리자가 권장되는 ID 및 장치 액세스 정책을 사용하고 조건부 액세스를 사용하기 위해 충족해야 하는 선행 조건에 대해 설명합니다. 또한 최상의 SSO(Single Sign-On) 환경을 위해 클라이언트 플랫폼을 구성하기 위한 권장 기본값에 대해 논의합니다.

## <a name="prerequisites"></a>필수 구성 요소

권장되는 ID 및 장치 액세스 정책을 사용하려면 조직에서 선행 요구 사항을 충족해야 합니다. 나열된 다양한 ID 및 인증 모델에 대한 요구 사항은 서로 다릅니다.

- 클라우드 전용
- PHS(암호 해시 동기화) 인증을 사용하는 하이브리드
- 통과 인증(PTA)을 사용하는 하이브리드
- 페더리트

다음 표에서는 설명된 경우를 제외하고 모든 ID 모델에 적용되는 선행 구성에 대한 자세한 내용을 제공합니다.

|구성|예외|라이선싱|
|---|:---:|---|
|[PHS를 구성합니다.](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)  유출된 자격 증명을 검색하고 위험 기반 조건부 액세스에 대해 이 기능을 사용하도록 설정해야 합니다. **참고:** 이는 조직에서 페더러드 인증을 사용하는지 여부에 관계없이 필요합니다.|클라우드 전용|Microsoft 365 E3 혹은 E5|
|[원활한 Single Sign-On을](/azure/active-directory/connect/active-directory-aadconnect-sso) 사용하도록 설정하여 사용자가 조직 네트워크에 연결된 조직 장치에 있는 경우 자동으로 로그인합니다.|클라우드 전용 및 페더|Microsoft 365 E3 혹은 E5|
|[명명된 위치를 구성합니다.](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) Azure AD ID 보호는 모든 사용 가능한 세션 데이터를 수집하고 분석하여 위험 점수를 생성합니다. Azure AD 명명된 위치 구성에서 네트워크에 대한 조직의 공용 IP 범위를 지정하는 것이 좋습니다. 이러한 범위에서 오는 트래픽에는 위험 점수가 감소하고 조직 환경 외부에서 오는 트래픽에는 더 높은 위험 점수가 부여됩니다.||Microsoft 365 E3 혹은 E5|
|[모든 사용자를 SSPR(셀프 서비스 암호 재설정) 및 MFA(다단계 인증)에 등록합니다.](/azure/active-directory/authentication/concept-registration-mfa-sspr-converged) Azure AD 다단계 인증에 사용자를 미리 등록하는 것이 좋습니다. Azure AD ID 보호는 Azure AD 다단계 인증을 사용하여 추가 보안 확인을 수행하도록 합니다. 또한 최상의 로그인 환경을 위해 사용자가 디바이스에 Microsoft Authenticator [](/azure/active-directory/user-help/microsoft-authenticator-app-how-to) 앱과 Microsoft 회사 포털 앱을 설치하는 것이 좋습니다. 이러한 앱은 각 플랫폼의 앱 스토어에서 설치할 수 있습니다.||Microsoft 365 E3 혹은 E5|
|[도메인에 가입된 컴퓨터의](/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)자동 장치 등록을 Windows. 조건부 액세스는 앱에 연결하는 장치가 도메인에 가입되어 있는지 또는 규격인지 확인 합니다. Windows 컴퓨터에서 이 기능을 지원하려면 Azure AD를 사용하여 장치를 등록해야 합니다.  이 문서에서는 자동 장치 등록을 구성하는 방법에 대해 설명합니다.|클라우드 전용|Microsoft 365 E3 혹은 E5|
|**사용자의 지원 팀 준비**. MFA를 완료할 수 없는 사용자에 대한 계획을 시행합니다. 정책 제외 그룹에 추가하거나 새 MFA 정보를 등록하는 것일 수 있습니다. 이러한 보안에 중요한 변경을 적용하기 전에 실제 사용자가 요청을 하는지 확인해야 합니다. 사용자의 관리자에 대해 승인을 통해 도움을 주도록 요구하는 것이 효과적인 단계입니다.||Microsoft 365 E3 혹은 E5|
|[온-프레미스 AD에 대한 암호 쓰기 저장 구성](/azure/active-directory/active-directory-passwords-getting-started). 암호 쓰기 저장을 사용하면 Azure AD에서 높은 위험 계정 손상이 감지될 때 사용자가 자신의온-프레미스 암호를 변경해야 할 수 있습니다. Azure AD 커넥트 설정의 선택적 기능 화면에서 암호 쓰기  저장을 사용하도록 설정하거나 설치 커넥트 방법 중 하나를 사용하여 이 기능을 사용하도록 설정할 수 Windows PowerShell.|클라우드 전용|Microsoft 365 E3 혹은 E5|
|[Azure AD 암호 보호를 구성합니다.](/azure/active-directory/authentication/concept-password-ban-bad) Azure AD 암호 보호에서는 알려진 취약한 암호와 해당 변형을 감지하고 차단하며 조직에 관련된 추가 취약한 용어를 차단할 수도 있습니다. 기본 전역 금지 암호 목록은 Azure AD 테넌트의 모든 사용자에게 자동으로 적용됩니다. 사용자 지정 금지 암호 목록에서 추가 항목을 정의할 수 있습니다. 사용자가 암호를 변경하거나 재설정하면 해당 금지된 암호 목록은 강력한 암호를 사용하도록 확인됩니다.||Microsoft 365 E3 혹은 E5|
|[ID Azure Active Directory 사용.](/azure/active-directory/identity-protection/overview-identity-protection) Azure AD ID 보호를 사용하면 조직의 ID에 영향을 주는 잠재적인 취약점을 감지하고 로그인 위험 및 사용자 위험을 낮음, 중간, 높음으로 자동 수정 정책을 구성할 수 있습니다.||Microsoft 365 E5 추가 Microsoft 365 E3 또는 E5 보안 추가 기능을 사용할 수 있습니다.|
|**사용자 및 Exchange Online** [온라인에](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) 대해 최신 [비즈니스용 Skype 사용하도록 설정](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) 최신 인증은 MFA를 사용하기 위한 선행 단계입니다. 최신 인증은 Office 2016 및 2019 클라이언트, SharePoint 및 비즈니스용 OneDrive.||Microsoft 365 E3 혹은 E5|
|Azure [AD에 대한 지속적인 액세스 평가를](microsoft-365-continuous-access-evaluation.md) 사용하도록 설정 지속적인 액세스 평가는 활성 사용자 세션을 사전적으로 종료하고 거의 실시간으로 테넌트 정책 변경을 적용합니다.||Microsoft 365 E3 혹은 E5|
|

## <a name="recommended-client-configurations"></a>권장되는 클라이언트 구성

이 섹션에서는 사용자에게 최상의 SSO 환경을 제공하기 위해 권장하는 기본 플랫폼 클라이언트 구성과 조건부 액세스에 대한 기술 전제 조건에 대해 설명합니다.

### <a name="windows-devices"></a>Windows 장치

Azure는 Windows 10 및 Azure AD 둘 다에서 가능한 원활한 SSO 환경을 제공하도록 설계되어 있는 Windows 10(버전 2004 이상)를 권장합니다. 직장 또는 학교에서 발급한 장치는 Azure AD에 직접 가입하도록 구성하거나 조직에서 사내 AD 도메인 가입을 사용하는 경우 해당 장치를 [자동으로 Azure AD에](/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)등록하도록 구성해야 합니다.

BYOD Windows 장치의 경우 사용자는 직장 또는 학교 계정 추가 **를 사용할 수 있습니다.** Windows 10 디바이스의 Google Chrome 브라우저 사용자는 사용자와 [](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) 동일한 원활한 로그인 환경을 제공하려면 확장을 Microsoft Edge 합니다. 또한 조직에 도메인에 가입된 Windows 8 또는 8.1 장치가 있는 경우 비보안 컴퓨터에 대해 Microsoft Workplace Join을 Windows 10 있습니다. [Azure AD에](https://www.microsoft.com/download/details.aspx?id=53554) 디바이스를 등록하기 위해 패키지를 다운로드합니다.

### <a name="ios-devices"></a>iOS 장치

조건부 액세스 또는 [MFA 정책을 Microsoft Authenticator](/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) 장치에 앱 앱을 설치하는 것이 좋습니다. 최소한 사용자가 회사 또는 학교 계정을 추가하여 Azure AD에 디바이스를 등록하도록 요청하거나 Intune 회사 포털 앱을 설치하여 장치를 관리에 등록할 때 앱을 설치해야 합니다. 이는 구성된 조건부 액세스 정책에 따라 다를 수 있습니다.

### <a name="android-devices"></a>Android 장치

조건부 액세스 [정책이 배포되기 Intune 회사 포털](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) 또는 특정 인증 시도 [중에](/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) Microsoft Authenticator 앱 및 앱 앱을 설치하는 것이 좋습니다. 앱 설치 후 사용자에게 Azure AD에 등록하거나 사용자의 장치를 Intune에 등록할 것을 요구할 수 있습니다. 이는 구성된 조건부 액세스 정책에 따라 다를 수 있습니다.

또한 조직 소유 디바이스를 Android for Work 또는 Samsung Knox를 지원하는 OEM 및 버전에서 표준화하여 메일 계정을 Intune MDM 정책에 의해 관리 및 보호할 수 있도록 하는 것이 좋습니다.

### <a name="recommended-email-clients"></a>권장되는 메일 클라이언트

다음 전자 메일 클라이언트는 최신 인증 및 조건부 액세스를 지원합니다.

|플랫폼|클라이언트|버전/참고|
|---|---|---|
|**Windows**|Outlook|2019, 2016, 2013 <p> [최신 인증 사용](../../admin/security-and-compliance/enable-modern-authentication.md) <p> [필수 업데이트](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|iOS용 Outlook|[최신](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Android용 Outlook|[최신](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2019 및 2016|
|**Linux**|지원되지 않음||
|

### <a name="recommended-client-platforms-when-securing-documents"></a>문서를 보호할 때 권장되는 클라이언트 플랫폼

보안 문서 정책이 적용된 경우 다음 클라이언트를 권장합니다.

|플랫폼|Word/Excel/PowerPoint|OneNote|OneDrive 앱|SharePoint 앱|[OneDrive 동기화 클라이언트](/onedrive/enable-conditional-access)|
|---|---|---|---|---|---|
|Windows 8.1|지원|지원|해당 없음|해당 없음|지원|
|Windows 10|지원|지원|해당 없음|해당 없음|지원|
|Android|지원|지원|지원|지원|해당 없음|
|iOS|지원|지원|지원|지원|해당 없음|
|macOS|지원|지원|해당 없음|해당 없음|지원되지 않음|
|Linux|지원되지 않음|지원되지 않음|지원되지 않음|지원되지 않음|지원되지 않음|
|

### <a name="microsoft-365-client-support"></a>Microsoft 365 클라이언트 지원

서버의 클라이언트 지원에 Microsoft 365 다음 문서를 참조하세요.

- [Microsoft 365 클라이언트 앱 지원 - 조건부 액세스](../../enterprise/microsoft-365-client-support-conditional-access.md)
- [Microsoft 365 클라이언트 앱 지원 - 다단계 인증](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md)

## <a name="protecting-administrator-accounts"></a>관리자 계정 보호

Microsoft 365 E3 또는 E5 또는 별도의 Azure AD Premium P1 또는 P2 라이선스의 경우 수동으로 만든 조건부 액세스 정책을 사용하여 관리자 계정에 대해 MFA를 요구할 수 있습니다. 자세한 [내용은 조건부 액세스: 관리자에게 MFA](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) 요구를 참조합니다.

조건부 Microsoft 365 Office 365 지원하지 않는 버전 또는 모든 계정의 경우 [](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) 보안 기본값을 사용하도록 설정하여 모든 계정에 대해 MFA를 요구할 수 있습니다.

다음은 몇 가지 추가 권장 사항입니다.

- [Azure AD Privileged Identity Management](/azure/active-directory/privileged-identity-management/pim-getting-started) 사용하여 영구 관리 계정 수를 줄입니다.
- [권한이 부여된 액세스 관리를](../../compliance/privileged-access-management-overview.md) 사용하여 중요한 데이터에 대한 액세스 또는 중요한 구성 설정에 대한 액세스 권한이 있는 기존 권한 있는 관리자 계정을 사용할 수 있는 침해로부터 조직을 보호합니다.
- 관리에만 Microsoft 365 할당된 [](../../admin/add-users/about-admin-roles.md) 별도의 계정을 *만들고 사용* 관리자는 정기적인 비관리용에 대한 자체 사용자 계정을 가지고 있으며, 필요한 경우 관리 계정을 사용하여 역할 또는 작업 기능과 관련된 작업을 완료해야 합니다.
- Azure [AD에서](/azure/active-directory/admin-roles-best-practices) 권한 있는 계정을 보안하기 위한 모범 사례를 따르하세요.

## <a name="next-step"></a>다음 단계

[![2단계: 공용 ID를 구성하고 조건부 액세스 정책에 액세스합니다.](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-2.png)](identity-access-policies.md)

[공통 ID 및 장치 액세스 정책 구성](identity-access-policies.md)