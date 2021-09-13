---
title: 사용자에 대한 다단계 Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: MFA(다단계 인증)는 강력한 암호와 추가 확인 방법을 모두 사용합니다.
ms.openlocfilehash: d0f88043ecaa4d2dd990f74661e904351db97524
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59186836"
---
# <a name="multifactor-authentication-for-microsoft-365"></a>사용자에 대한 다단계 Microsoft 365

암호는 컴퓨터 또는 온라인 서비스에 로그인을 인증하는 가장 일반적인 방법입지만 가장 취약하기도 합니다. 사용자는 단순한 암호를 선택 하기도 하고 다른 컴퓨터 및 서비스에서 동일한 암호를 사용하기도 합니다.

로그인에 대한 추가 보안 수준을 제공하려면 강력한 암호와 다음을 기반으로 하는 추가 확인 방법을 모두 사용하는 MFA(다단계 인증)를 사용해야 합니다.

- 사용자가 보유한 것 중 스마트폰과 같이 쉽게 복제할 수 없는 장치입니다.
- 사용자의 지문, 얼굴 또는 기타 생체 인식 특성과 같이 고유하고 생물학적으로 가지고 있는 것입니다.

추가 확인 방법은 사용자의 암호가 확인될 때까지 사용되지 않습니다. 사용자의 강력한 암호가 노출 되었다 하더라도 MFA를 사용하면 공격자는 사용자의 스마트폰이나 지문을 가지고 있지 않기 때문에 로그인을 완성할 수 없습니다.

## <a name="mfa-support-in-microsoft-365"></a>Microsoft 365에서 MFA 지원

기본적으로 다음을 사용하여 Microsoft 365 및 Office 365가 사용자 계정의 MFA를 지원 합니다.

- 사용자가 확인 코드를 입력 하도록 휴대폰으로 전송 된 문자 메시지
- 전화 통화
- Microsoft Authenticator 스마트폰 앱

두 경우 모두 MFA 로그인은 추가 확인을 위해 "쉽게 중복되지 않는 항목"을 사용합니다. Microsoft 365 및 Office 365에서 MFA를 사용 설정 하기 위한 다양한 방법이 있습니다.

- 보안 기본값으로
- 조건부 액세스 정책으로
- 각 개별 사용자 계정에 대해 (권장 하지 않음)

이러한 방법은 Microsoft 365 요금제에 기반합니다.

|계획|권장 사항|고객 유형|
|---|---|---|
|모든 Microsoft 365 요금제|모든 사용자 계정에 대해 MFA를 필수로 요청하는 보안 기본값을 사용합니다. <p> 개별 사용자 계정에 대해 사용자별 MFA를 구성할 수도 있지만 권장되지는 않습니다.|소규모 기업|
|Microsoft 365 Business Premium <p> Microsoft 365 E3 <p> Azure AD(Azure Active Directory) Premium P1 라이선스|조건부 액세스 정책을 사용하여 그룹 멤버 자격, 앱 또는 기타 기준에 따라 사용자 계정에 MFA를 요구합니다.|소규모 기업에서 기업까지|
|Microsoft 365 E5 <p> Azure AD Premium P2 라이선스|Azure AD ID 보호를 사용하여 로그인 위험 기준에 따라 MFA를 요구합니다.|엔터프라이즈|
||||

### <a name="security-defaults"></a>보안 기본값

보안 기본값은 2019년 10월 21일 이후에 개발된 Microsoft 365 및 Office 365 유료 또는 평가판 구독을위한 새로운 기능입니다. 이러한 구독에는 보안 기본값이 설정 되어 있습니다.

- Microsoft Authenticator 앱의 모든 사용자가 MFA를 사용 하도록 요구 합니다.
- 레거시 인증을 차단합니다.

사용자는 스마트 폰에서 Microsoft Authenticator 앱으로 MFA에 14일 간 등록할 수 있으며, 이는 보안 기본값이 활성화된 후 처음 로그인 할 때부터 시작됩니다. 14일이 지나면 MFA 등록이 완료될 때까지 사용자가 로그인할 수 없습니다.

보안 기본값은 모든 조직이 기본적으로 사용되는 사용자 로그인에 대한 기본 보안 수준을 갖도록 합니다. 조건부 액세스 정책으로 MFA를 위해 보안 기본값을 비활성화할 수 있습니다.

Azure 포털의 Azure AD에 대해 **속성** 창에서 보안 기본값을 사용하거나 사용하지 않도록 설정할 수 있습니다.

![디렉터리 속성 페이지의 그림입니다.](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

모든 Microsoft 365 요금제에 보안 기본값을 사용할 수 있습니다.

자세한 정보는 이 [보안 기본값 개요](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)를 참조하세요.

### <a name="conditional-access-policies"></a>조건부 액세스 정책

조건부 액세스 정책은 로그인 평가 및 허용 조건을 지정하는 규칙 집합입니다. 예를 들어 다음과 같은 조건부 액세스 정책을 만들 수 있습니다.

- 사용자 계정 이름이 Exchange, 사용자, 암호, 보안, SharePoint 또는 전역 관리자 역할이 할당된 사용자의 그룹의 구성원인 경우, 액세스를 허용하기 전에 MFA를 요구합니다.

이 정책을 사용하면 이들 관리자 역할이 할당되거나 할당이 해제될 때 MFA에 대한 개별 사용자 계정을 구성하는 대신 그룹 멤버 자격을 기반으로 MFA를 요구할 수 있습니다.

특정 앱에 MFA를 요구하거나 Windows 10을 실행하는 노트북과 같은 준수 장치에서 로그인을 수행하는 등의 고급 기능을 위해 조건부 액세스 정책을 사용할 수 있습니다.

Azure 포털의 Azure AD의 **보안** 창에서 조건부 액세스 정책을 구성합니다.

![조건부 액세스의 메뉴 옵션 그림입니다.](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

조건부 액세스 정책을 사용할 수 있습니다

- Microsoft 365 Business Premium
- Microsoft 365 E3 및 E5
- Azure AD Premium P1 및 Azure AD Premium P2 라이선스

Microsoft 365 Business Premium이 있는 소규모 기업의 경우 다음 단계를 통해 조건부 액세스 정책을 손쉽게 사용할 수 있습니다.

1. MFA를 필요로 하는 사용자 계정을 포함할 그룹을 만듭니다.
2. **전역 관리자에 MFA 요구** 정책을 사용 가능하게 합니다.
3. 다음 설정을 사용하여 그룹 기반 조건부 액세스 정책을 만듭니다.
    - 할당 > 사용자 및 그룹: 위의 단계 1에서 지정한 그룹 이름
    - 할당 > 클라우드 앱 혹은 활동: 모든 클라우드 앱
    - 액세스 제어 > 부여 > 액세스 부여 > 단계 인증 요구
4. 정책 사용 설정
5. 위의 1 단계에서 만든 그룹에 사용자 계정을 추가하고 테스트 합니다.
6. 추가 사용자 계정에 MFA를 요구 하려면 1 단계에서 만든 그룹에 해당 사용자 계정을 추가합니다.

이 조건부 액세스 정책을 사용하면 사용자가 원하는 진도에 맞춰 MFA 요구 사항을 롤아웃할 수 있습니다.

Enterprises는 [공통 조건부 액세스 정책](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)을 사용하여 다음 정책을 구성합니다.

- [관리자에게 MFA 요구](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [모든 사용자에게 MFA 요구](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [레거시 인증 차단](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

자세한 내용은 이 [조건부 액세스 개요](/azure/active-directory/conditional-access/overview)를 참조하세요.

### <a name="azure-ad-identity-protection"></a>Azure AD ID 보호

Azure AD ID 보호 기능을 사용하여 [로그인 위험이 중간에서 높음일 때 MFA를 요구](../../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk)하는 추가 조건부 액세스 정책을 만들 수 있습니다.

다음에서는 Azure AD ID 보호 및 위험 기반 조건부 액세스 정책을 사용할 수 있습니다.

- Microsoft 365 E5
- Azure AD Premium P2 라이선스

자세한 내용은 이 [Azure AD ID 보호 개요](/azure/active-directory/identity-protection/overview-identity-protection)를 참조하세요.

### <a name="legacy-per-user-mfa-not-recommended"></a>사용자당 레거시 MFA(권장하지 않음)

사용자 계정 로그인에 MFA를 요구하기 위해 보안 기본값이나 조건부 액세스 정책을 사용해야 합니다. 하지만 둘 다 사용할 수 없는 경우라면 Microsoft는 관리자 권한이 있는 사용자(특히, 모든 구독에 대한 권역 관리자 역할을 가진 사용자)에 MFA를 권장 합니다.

사용자 계정의 활성 사용자 창에서 개별 사용자 계정에 대해 MFA를 Microsoft 365 관리 센터. <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank"></a>

![활성 사용자 페이지의 다단계 인증 옵션 그림.](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

사용 설정 되면, 사용자가 다음에 로그인 할 때에 MFA를 등록하고 추가 확인 방법을 선택하라는 메시지가 표시됩니다.

### <a name="using-these-methods-together"></a>이 방법들을 함께 사용

이 표는 보안 기본값, 조건부 액세스 정책 및 사용자별 계정 설정으로 MFA를 활성화한 결과를 보여줍니다.

|*항목*|사용|사용 안 함|보조 인증 방법|
|---|---|---|---|
|**보안 기본값**|조건부 액세스 정책을 사용할 수 없습니다.|조건부 액세스 정책을 사용할 수 있습니다|Microsoft Authenticator 앱|
|**조건부 액세스 정책**|사용하도록 설정된 경우 보안 기본값을 사용하도록 설정할 수 없습니다.|상기 수단을 모두 사용하지 않도록 설정한 경우, MFA 등록 중 사용자가 지정한 |MFA 등록 중 사용자 지정|
|**사용자당 레거시 MFA(권장하지 않음)**|각 로그인에서 MFA를 요구 하는 보안 기본값과 조건부 액세스 정책을 재정의 합니다.|보안 기본값과 조건부 액세스 정책에 의해 재정의|MFA 등록 중 사용자 지정|
||||

보안 기본값을 사용하면 다음 로그인 시 모든 새 사용자에게 MFA 등록 및 Microsoft Authenticator 앱 사용을 요구하는 메시지가 표시됩니다.

## <a name="ways-to-manage-mfa-settings"></a>MFA 설정 관리 방법

MAF 설정을 관리하는 두 가지 방법이 있습니다.

Azure 포털에서 다음을 할 수 있습니다.

- 보안 기본값을 사용 설정 혹은 사용 해제
- 조건부 액세스 정책 구성

이 Microsoft 365 관리 센터 사용자 및 서비스 MFA 설정을 <a href="https://go.microsoft.com/fwlink/p/?linkid=2169174" target="_blank">구성할 수 있습니다.</a>

## <a name="next-steps"></a>다음 단계

[Microsoft 365 MFA 설정](set-up-multi-factor-authentication.md)

## <a name="related-content"></a>관련 콘텐츠

[다단계 인증 켜기](../../business-video/turn-on-mfa.md)(비디오)\
[휴대폰의 다단계 인증 켜기](../../business-video/set-up-mfa.md)(비디오)