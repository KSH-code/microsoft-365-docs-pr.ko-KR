---
title: 1단계.MFA를 사용하여 하이브리드 작업자에 대 한 로그인 보안 강화
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: 하이브리드 작업자는 MFA(다단계 인증)를 사용하여 로그인해야 합니다.
ms.openlocfilehash: d59f990cd7acf576247d75e6544ad045179e3c81
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59189049"
---
# <a name="step-1-increase-sign-in-security-for-hybrid-workers-with-mfa"></a>1단계.MFA를 사용하여 하이브리드 작업자에 대 한 로그인 보안 강화

하이브리드 작업자의 로그인에 대한 보안을 강화하려면 MFA(다단계 인증)를 사용합니다. MFA에서는 사용자 로그인이 사용자 계정 비밀번호 외에 추가 확인을 받아야합니다. 악의적인 사용자가 사용자 계정 암호를 확인하더라도 액세스 권한이 부여되기 전에 스마트폰으로 전송되는 문자 메시지와 같은 추가 확인에 응답 할 수 있어야 합니다.

![올바른 암호와 추가적인 확인을 수행하면 로그인에 성공합니다.](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

하이브리드 작업자, 특히 관리자를 포함한 모든 사용자에게 MFA를 강력히 권장합니다.

사용자가 Microsoft 365 계획에 따라 MFA를 사용하도록하는 방법에는 세 가지가 있습니다.

|계획  |권장 사항  |
|---------|---------|
|모든 Microsoft 365 요금제(Azure AD Premium P1 또는 P2 라이선스 제외)     |[Azure AD](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)에서 보안 기본값을 사용하도록 설정 합니다. Azure AD의 보안 기본값에는 사용자 및 관리자를 위한 MFA가 포함됩니다.   |
|Microsoft 365 E3(Azure AD Premium P1 라이선스 포함)     | [공통 조건부 액세스 정책](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)을 사용하여 다음 정책을 구성합니다. <br>- [관리자에게 MFA 요구](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [모든 사용자에 대해 MFA 요구](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [레거시 인증 차단](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5(Azure AD Premium P2 라이선스 포함)     | Azure AD ID 보호를 활용하여 다음 정책을 만들어 Microsoft의 [권장 조건부 액세스 및 관련 정책 집합](../security/office-365-security/identity-access-policies.md)을 구현하세요.<br> - [로그인 위험이 중간 이상인 경우 MFA 필요](../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [최신 인증을 지원하지 않는 클라이언트 차단](../security/office-365-security/identity-access-policies.md#block-clients-that-dont-support-multi-factor)<br>- [위험이 높은 사용자는 암호를 변경해야 함](../security/office-365-security/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |

## <a name="security-defaults"></a>보안 기본값

보안 기본값은 2019년 10월 21일 이후에 개발된 Microsoft 365 및 Office 365 유료 또는 평가판 구독을위한 새로운 기능입니다. 이 구독에는 보안 기본값이 설정되어 있으며 ***모든 사용자가 Microsoft Authenticator 앱과 함께 MFA를 사용해야 합니다***.
 
사용자는 스마트 폰에서 Microsoft Authenticator 앱으로 MFA에 14일 간 등록할 수 있으며, 이는 보안 기본값이 활성화된 후 처음 로그인 할 때부터 시작됩니다. 14일이 지나면 MFA 등록이 완료될 때까지 사용자가 로그인할 수 없습니다.

보안 기본값은 모든 조직이 기본적으로 사용되는 사용자 로그인에 대한 기본 보안 수준을 갖도록 합니다. 조건부 액세스 정책 또는 개별 계정으로 MFA를 위해 보안 기본값을 비활성화할 수 있습니다.

자세한 정보는 이 [보안 기본값 개요](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)를 참조하세요.

## <a name="conditional-access-policies"></a>조건부 액세스 정책

조건부 액세스 정책은 로그인 평가 및 허용 조건을 지정하는 규칙 집합입니다. 예를 들어 다음과 같은 조건부 액세스 정책을 만들 수 있습니다.

- 사용자 계정 이름이 Exchange, 사용자, 암호, 보안, SharePoint 또는 전역 관리자 역할이 할당된 사용자의 그룹의 구성원인 경우, 액세스를 허용하기 전에 MFA를 요구합니다.

이 정책을 사용하면 이들 관리자 역할이 할당되거나 할당이 해제될 때 MFA에 대한 개별 사용자 계정을 구성하는 대신 그룹 멤버 자격을 기반으로 MFA를 요구할 수 있습니다.

Windows 10을 실행하는 노트북과 같은 호환 장치에서 로그인을 요구하는 등 고급 기능을 위해 조건부 액세스 정책을 사용할 수도 있습니다.

조건부 액세스에는 Microsoft 365 E3 및 E5에 포함된 Azure AD Premium P1 라이선스가 필요합니다.

자세한 내용은 이 [조건부 액세스 개요](/azure/active-directory/conditional-access/overview)를 참조하세요.

## <a name="azure-ad-identity-protection-support"></a>Azure AD ID 보호 지원

Azure AD ID 보호 기능을 사용하여 다음과 같이 조건을 부여하는 추가 조건부 액세스 정책을 만들 수 있습니다.

- 로그인의 위험이 중간 또는 높은으로 판단되면, MFA를 요구합니다.

Azure AD ID 보호 기능은 Microsoft 365 E5에 포함된 Azure AD Premium P2 라이선스를 필요로 합니다.

자세한 내용은 [위험에 기반한 조건부 액세스](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk#require-mfa-medium-or-high-sign-in-risk-users)를 참조하세요.

Azure AD ID 보호를 사용하여 사용자가 MFA에 등록하도록 요구하는 정책을 만들 수도 있습니다. 더 자세한 내용은 [Azure AD 다단계 인증 등록 정책 구성](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)을 참조하세요.


## <a name="using-these-methods-together"></a>이 방법들을 함께 사용

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

## <a name="let-your-users-reset-their-own-passwords"></a>사용자가 암호를 직접 재설정할 수 있도록 허용

사용자는 셀프 서비스 암호 재설정(SSPR)을 사용하여 IT 직원이 없어도 암호를 재설정할 수 있습니다. 사용자는 언제 어디에서나 암호를 신속하게 재설정할 수 있습니다. 더 자세한 내용은 [Azure AD 셀프 서비스 암호 재설정 배포 계획](/azure/active-directory/authentication/howto-sspr-deployment)을 참조하세요.

## <a name="sign-in-to-saas-apps-with-azure-ad"></a>Azure AD를 사용하여 SaaS 앱에 로그인

Azure AD는 사용자에게 클라우드 인증을 제공할 뿐만 아니라 사내, 마이크로소프트 클라우드 또는 다른 클라우드에 있는 모든 애플리케이션을 보호하는 중요한 방법이 될 수도 있습니다. [Azure AD](/azure/active-directory/manage-apps/plan-an-application-integration)에 앱을 통합하면 하이브리드 작업자들이 필요로 하는 응용 프로그램을 쉽게 검색하고 안전하게 로그인할 수 있습니다.

## <a name="admin-technical-resources-for-mfa-and-identity"></a>MFA 및 ID에 대한 관리자 기술 리소스

- [Azure AD를 사용하여 원격 작업을 수행하는 데 도움이 되는 상위 5가지 방법](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/top-5-ways-your-azure-ad-can-help-you-enable-remote-work/ba-p/1144691)
- [Microsoft 365의 ID 로드맵](../enterprise/identity-roadmap-microsoft-365.md)
- [Azure Academy Azure AD 교육 비디오](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)

## <a name="results-of-step-1"></a>1단계 결과

MFA를 배포한 후 사용자는 다음 사항에 해당됩니다.

- 로그인에 MFA를 사용해야 합니다.
- MFA 등록 절차를 완료했으며 모든 로그인에 MFA를 사용하고 있습니다.
- SSPR을 사용하여 암호를 직접 재설정할 수 있습니다.

## <a name="next-step"></a>다음 단계

[![2단계: 온-프레미스 앱 및 서비스에 대한 원격 액세스 제공](../media/empower-people-to-work-remotely/remote-workers-step-grid-2.png)](empower-people-to-work-remotely-remote-access.md)

온 프레미스 앱 및 서비스에 대한 원격 액세스를 제공하려면 [2단계](empower-people-to-work-remotely-remote-access.md)를 계속 진행하세요.