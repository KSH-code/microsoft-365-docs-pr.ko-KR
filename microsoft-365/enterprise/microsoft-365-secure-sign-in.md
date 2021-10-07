---
title: Microsoft 365 테넌트에 사용자 로그인 보안 기능
f1.keywords:
- NOCSH
author: kelleyvice-msft
ms.author: kvice
manager: laurawi
ms.date: 09/30/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365initiative-coredeploy
ms.custom: ''
description: 사용자가 MFA(다단계 인증) 및 기타 기능을 사용하여 안전하게 로그인하도록 합니다.
ms.openlocfilehash: 9c29bddee33ee7e06fcaf24bfff8649a12320e9c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60200104"
---
# <a name="secure-user-sign-ins-to-your-microsoft-365-tenant"></a>Microsoft 365 테넌트에 사용자 로그인 보안 기능

사용자 로그인의 보안을 강화하려면 다음을 수행합니다.

- 비즈니스용 Windows Hello 사용
- Azure AD(Azure Active Directory) 암호 보호 사용
- MFA(다단계 인증) 사용
- ID 및 장치 액세스 구성 배포
- Azure AD ID 보호를 사용하여 자격 증명 손상으로부터 보호

## <a name="windows-hello-for-business"></a>비즈니스용 Windows Hello

Windows 10 Enterprise의 비즈니스용 windows Hello는 Windows 장치에 로그인할 때 암호를 강력한 2 단계 인증으로 대체합니다. 2단계 인증 요소는 장치에 연결된 새로운 유형의 사용자 자격 증명과 생체 인식 또는 PIN입니다.

자세한 내용은 [비즈니스용 Windows Hello 개요](/windows/security/identity-protection/hello-for-business/hello-overview)를 참조하세요.


## <a name="azure-ad-password-protection"></a>Azure AD 암호 보호

Azure AD 암호 보호에서는 알려진 취약한 암호와 해당 변형을 감지하고 차단하며 조직에 관련된 추가 취약한 용어를 차단할 수도 있습니다. 기본 전역 금지 암호 목록은 Azure AD 테넌트의 모든 사용자에게 자동으로 적용됩니다. 사용자 지정 금지 암호 목록에서 추가 항목을 정의할 수 있습니다. 사용자가 암호를 변경하거나 재설정하면 해당 금지된 암호 목록은 강력한 암호를 사용하도록 확인됩니다.

자세한 내용은 [Azure AD 암호 보호구성](/azure/active-directory/authentication/concept-password-ban-bad)을 참조하세요.

## <a name="mfa"></a>MFA

MFA에서는 사용자 로그인이 사용자 계정 비밀번호 외에 추가 확인을 받아야합니다. 악의적인 사용자가 사용자 계정 암호를 확인하더라도 액세스 권한이 부여되기 전에 스마트폰으로 전송되는 문자 메시지와 같은 추가 확인에 응답 할 수 있어야 합니다.

![올바른 암호와 추가적인 확인을 수행하면 로그인에 성공합니다.](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

MFA를 사용하는 첫 번째 단계는 ***모든 관리자 계정(예를 들어, 권한 있는 계정이라고도 함)에 해당 항목을 요청*** 하는 것입니다.

첫 번째 단계를 넘어서, Microsoft는 모든 사용자에 대해 MFA를 권장합니다.

Microsoft 365 플랜에 따라 관리자나 사용자가 MFA를 사용하도록 요청하는 데 세 가지 방법이 있습니다.

| 계획 | 권장 사항 |
|---------|---------|
|모든 Microsoft 365 요금제(Azure AD Premium P1 또는 P2 라이선스 제외)     |[Azure AD](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)에서 보안 기본값을 사용하도록 설정 합니다. Azure AD의 보안 기본값에는 사용자 및 관리자를 위한 MFA가 포함됩니다.   |
|Microsoft 365 E3(Azure AD Premium P1 라이선스 포함)     | [공통 조건부 액세스 정책](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)을 사용하여 다음 정책을 구성합니다. <br>- [관리자에게 MFA 요구](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [모든 사용자에 대해 MFA 요구](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [레거시 인증 차단](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5(Azure AD Premium P2 라이선스 포함)     | Azure AD ID 보호를 활용하여 다음 두 정책을 만들어 Microsoft의 [권장 조건부 액세스 및 관련 정책 집합](../security/office-365-security/identity-access-policies.md)을 구현하세요.<br> - [로그인 위험이 중간 이상인 경우 MFA 필요](../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [위험이 높은 사용자는 암호를 변경해야 함](../security/office-365-security/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |

### <a name="security-defaults"></a>보안 기본값

보안 기본값은 2019년 10월 21일 이후에 개발된 Microsoft 365 및 Office 365 유료 또는 평가판 구독을위한 새로운 기능입니다. 이 구독에는 보안 기본값이 설정되어 있으며 ***모든 사용자가 Microsoft Authenticator 앱과 함께 MFA를 사용해야 합니다***.
 
사용자는 스마트 폰에서 Microsoft Authenticator 앱으로 MFA에 14일 간 등록할 수 있으며, 이는 보안 기본값이 활성화된 후 처음 로그인 할 때부터 시작됩니다. 14일이 지나면 MFA 등록이 완료될 때까지 사용자가 로그인할 수 없습니다.

보안 기본값은 모든 조직이 기본적으로 사용되는 사용자 로그인에 대한 기본 보안 수준을 갖도록 합니다. 조건부 액세스 정책 또는 개별 계정으로 MFA를 위해 보안 기본값을 비활성화할 수 있습니다.

자세한 정보는 [보안 기본값 개요](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)를 참조하세요.

### <a name="conditional-access-policies"></a>조건부 액세스 정책

조건부 액세스 정책은 로그인이 평가되고 액세스 권한이 부여되는 조건을 지정하는 규칙 집합입니다. 예를 들어 다음과 같은 조건부 액세스 정책을 만들 수 있습니다.

- 사용자 계정 이름이 Exchange, 사용자, 암호, 보안, SharePoint **Exchange 관리자**, **SharePoint 관리자** 또는 **전역 관리자** 역할이 할당된 사용자 그룹의 구성원인 경우, 액세스를 허용하기 전에 MFA가 필요합니다.

이 정책을 사용하면 이들 관리자 역할이 할당되거나 할당이 해제될 때 MFA에 대한 개별 사용자 계정을 구성하는 대신 그룹 멤버 자격을 기반으로 MFA를 요구할 수 있습니다.

Windows 10을 실행하는 노트북과 같은 호환 장치에서 로그인을 요구하는 등 고급 기능을 위해 조건부 액세스 정책을 사용할 수도 있습니다.

조건부 액세스에는 Microsoft 365 E3 및 E5에 포함된 Azure AD Premium P1 라이선스가 필요합니다.

자세한 내용은 [조건부 액세스 개요](/azure/active-directory/conditional-access/overview)를 참조하세요.

### <a name="using-these-methods-together"></a>이 방법들을 함께 사용

다음 사항에 유의해야 합니다.

- 조건부 액세스 정책을 사용하도록 설정한 경우에는 보안 기본값을 사용할 수 없습니다.
- 보안 기본값이 활성화되어 있으면 조건부 액세스 정책을 활성화할 수 없습니다.

보안 기본값을 사용하면 모든 새 사용자에게 MFA 등록 및 Microsoft Authenticator 앱 사용을 요구하는 메시지가 표시됩니다. 

이 표는 보안 기본값 및 조건부 액세스 정책으로 MFA를 활성화한 결과를 보여줍니다.

| 메서드 | 사용 | 사용 안 함 | 추가 인증 방법 |
|:-------|:-----|:-------|:-------|
| **보안 기본값**  | 조건부 액세스 정책을 사용할 수 없습니다 | 조건부 액세스 정책을 사용할 수 있습니다 | Microsoft Authenticator 앱 |
| **조건부 액세스 정책** | 이 중 하나가 사용되는 경우 보안 기본값을 사용할 수 없습니다. | 상기 수단을 모두 사용하지 않도록 설정한 경우, MFA 등록 중 사용자가 지정한   | 보안 기본값을 사용할 수 있습니다  |
||||

## <a name="identity-and-device-access-configurations"></a>ID 및 장치 액세스 구성

ID 및 장치 액세스 설정과 정책은 권장되는 필수 기능 및 해당 설정이며, 이는 어떤 조건으로 지정된 액세스 요청이 부여되는지를 결정하는 조건부 액세스, Intune 및 Azure AD Identity Protection 정책과 함께 결합됩니다. 이 결정은 로그인의 사용자 계정, 사용 중인 장치, 사용자가 액세스하기 위해 사용하는 앱, 액세스 요청을 만든 위치, 요청 위험에 대한 평가를 기준으로 합니다. 이 기능을 사용하여 승인된 사용자와 장치만 중요한 리소스에 액세스할 수 있도록 할 수 있습니다.

>[!Note]
>Azure AD ID 보호 기능은 Microsoft 365 E5에 포함된 Azure AD Premium P2 라이선스를 필요로 합니다.
>

ID 및 장치 액세스 정책은 세 계층으로 사용하도록 정의됩니다. 

- 기준 보호는 앱과 데이터에 액세스하는 ID와 장치에 대한 최소 수준의 보안입니다.
- 중요 보호는 특정 데이터에 대한 추가 보안을 제공합니다. ID 및 장치에는 보안 및 장치 상태에 대해 더 높은 수준을 요구합니다.
- 규제가 엄격하거나 높은 수준으로 분류된 데이터를 포함하는 환경에 대한 보호는 높은 수준으로 분류되거나, 거래 비밀을 포함하거나, 데이터 규제가 적용되는 소량 데이터에 적합합니다. ID 및 장치에는 높은 수준의 보안 및 장치 상태 요구 사항이 많이 적용됩니다. 

해당 계층과 관련 구성은 데이터, ID 및 장치에 대해 일관된 수준의 보호를 제공합니다.

Microsoft Teams, Exchange Online 및 SharePoint에 대한 특정 설정을 포함하여 조직에서 ID 및 장치 액세스 정책을 구성하고 배포하는 것이 매우 좋습니다. 자세한 내용은 [ID 및 장치 액세스 구성](../security/office-365-security/microsoft-365-policies-configurations.md)을 참조하세요.

## <a name="azure-ad-identity-protection"></a>Azure AD ID 보호

이 섹션에서는 공격자가 사용자 계정 이름 및 암호를 확인하여 조직의 클라우드 서비스와 데이터에 액세스할 수 있는 자격 증명 손상으로부터 보호하는 정책을 구성하는 방법을 알아봅니다. Azure AD ID 보호는 공격자가 사용자 계정의 자격 증명을 손상시키는 것을 방지하는 데 도움이 되는 다양한 방법을 제공합니다.

Azure AD ID 보호를 사용하면 다음을 수행할 수 있습니다.

|기능|설명|
|:---------|:---------|
| 조직의 ID에서 잠재적인 취약점 확인 및 해결 | Azure AD는 기계 학습을 사용하여 로그인 및 로그인 후 활동과 같은 의심스러운 활동과 비정상적인 상태를 감지합니다. Azure AD ID 보호는 이 데이터를 사용하여 보고서를 생성하며 사용자가 문제를 평가하고 조치를 취할 수 있도록 경고를 생성합니다.|
|조직의 ID와 관련이 있는 의심스러운 동작을 감지하고 자동으로 대응|지정된 위험 수준에 도달했을 때 검색된 문제에 자동으로 대응하는 위험 기반 정책을 구성할 수 있습니다. 이러한 정책은 Azure AD 및 Microsoft Intune이 제공하는 다른 조건부 액세스 제어 외에도 액세스를 자동으로 차단하거나 암호 재설정 및 후속 로그인을 위해 Azure AD 다단계 인증을 요구하는 등의 수정 작업을 수행할 수 있습니다. |
| 의심스러운 사건을 조사하여 관리 작업으로 해결 | 보안 사건에 대한 정보를 사용하여 위험 이벤트를 조사할 수 있습니다. 기본 워크플로를 사용하여 조사를 추적하고 암호 재설정과 같은 수정 작업을 시작할 수 있습니다. |
|||

[Azure AD ID 보호에 대한 자세한 정보](/azure/active-directory/active-directory-identityprotection)를 참조하세요.

[Azure AD ID 보호를 사용하도록 설정하는 단계](/azure/active-directory/active-directory-identityprotection-enable)를 참조하세요.

## <a name="admin-technical-resources-for-mfa-and-secure-sign-ins"></a>MFA 및 보안 로그인에 대한 관리자 기술 리소스

- [Microsoft 365에 대한 MFA](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)
- [Microsoft 365의 ID 로드맵](identity-roadmap-microsoft-365.md)
- [Azure Academy Azure AD 교육 비디오](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [Azure 다단계 인증 등록 정책 구성](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)
- [ID 및 장치 액세스 구성](../security/office-365-security/microsoft-365-policies-configurations.md)

## <a name="next-step"></a>다음 단계

[사용자 계정 관리](manage-microsoft-365-accounts.md)
