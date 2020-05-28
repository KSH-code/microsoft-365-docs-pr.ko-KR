---
title: Microsoft 365에 대한 다단계 인증 사용
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 365의 다단계 인증에 대해 알아봅니다.
ms.openlocfilehash: e8ba304d145ca7227eea074556ff6efccd751ecf
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399149"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a>Microsoft 365에 대한 다단계 인증 사용

암호는 컴퓨터 또는 온라인 서비스에 대 한 로그인을 인증 하는 가장 일반적인 방법 이지만 가장 취약 합니다. 사용자는 여러 컴퓨터와 서비스에 대 한 로그인을 간편 하 게 선택 하 고 동일한 암호를 사용할 수 있습니다.

로그인에 대 한 추가 보안 수준을 제공 하려면 암호를 사용 하는 MFA (다단계 인증)와 다음을 기반으로 하는 추가 확인 방법을 사용 해야 합니다.

- 스마트 전화와 같이 쉽게 복제할 수 없는 항목입니다.
- 지문, 얼굴 또는 기타 생체 인식 특성과 같이 고유 하 고 biologically 있는 항목

사용자의 암호를 확인 한 후에는 추가 확인 방법이 적용 되지 않습니다. MFA를 사용 하 여 강력한 사용자 암호가 손상 된 경우에도 공격자는 로그인을 완료 하기 위해 스마트 전화나 지문을 갖고 있지 않습니다.

## <a name="mfa-support-in-microsoft-365"></a>Microsoft 365의 MFA 지원
기본적으로 Microsoft 365 및 Office 365에서는 다음을 사용 하 여 사용자 계정에 대 한 MFA를 지원 합니다.

- 사용자가 확인 코드를 입력 해야 하는 휴대폰으로 전송 되는 텍스트 메시지입니다.
- 전화 통화입니다.
- Microsoft Authenticator 스마트 폰 앱입니다.

두 경우 모두 MFA 로그인에서는 추가 확인을 위해 "쉽게 복제할 수 없는 항목" 방법을 사용 합니다.
Microsoft 365 및 Office 365에서 MFA를 사용 하도록 설정 하는 방법에는 여러 가지가 있습니다.

- 보안 기본값 사용
- 조건부 액세스 정책을 사용 하는 경우
- 개별 사용자 계정에 대해 (권장 하지 않음)

이러한 방법은 Microsoft 365 계획을 기반으로 합니다.
    
|계획  |권장 사항  | 고객 유형 |
|---------|---------|----------|
| 모든 Microsoft 365 계획 | 모든 사용자 계정에 대해 MFA가 필요한 보안 기본값을 사용 합니다. <br> 사용자별 계정 단위로 MFA를 요구할 수도 있지만이는 권장 되지 않습니다. | 소규모 기업 |
| Microsoft 365 Business Premium <br><br> Microsoft 365 E3 <br><br> Azure Active Directory (Azure AD) Premium P1 라이선스 | 조건부 액세스 정책을 사용 하 여 그룹 구성원, 앱 또는 기타 기준에 따라 사용자 계정에 대 한 MFA를 요구 합니다. | 중소 기업-기업 |
| Microsoft 365 E5 <br><br> Azure AD Premium P2 라이선스 | Azure AD Id 보호를 사용 하 여 로그인 위험 조건에 따라 MFA를 요구 합니다. |  엔터프라이즈 |
||||

### <a name="security-defaults"></a>보안 기본값

보안 기본값은 2019년 10월 21일 이후에 개발된 Microsoft 365 및 Office 365 유료 또는 평가판 구독을위한 새로운 기능입니다. 이러한 구독은 다음과 같은 보안 기본값을 설정 합니다.

- 모든 사용자가 Microsoft Authenticator 앱과 함께 MFA를 사용 해야 합니다.
- 레거시 인증을 차단 합니다.

사용자는 스마트 폰에서 Microsoft Authenticator 앱으로 MFA에 14일 간 등록할 수 있으며, 이는 보안 기본값이 활성화된 후 처음 로그인 할 때부터 시작됩니다. 14일이 지나면 MFA 등록이 완료될 때까지 사용자가 로그인할 수 없습니다.

보안 기본값은 모든 조직이 기본적으로 사용되는 사용자 로그인에 대한 기본 보안 수준을 갖도록 합니다. 보안 기본값을 사용 하지 않도록 설정 하려면 MFA가 조건부 액세스 정책에 우선 합니다.

Azure portal의 Azure AD에 대 한 **속성** 창에서 보안 기본값을 사용 하거나 사용 하지 않도록 설정 합니다.

![](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

보안 기본값을 Microsoft 365 계획에 사용할 수 있습니다.

자세한 정보는 이 [보안 기본값 개요](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)를 참조하세요. 

### <a name="conditional-access-policies"></a>조건부 액세스 정책

조건부 액세스 정책은 로그인 평가 및 허용 조건을 지정하는 규칙 집합입니다. 예를 들어 다음과 같은 조건부 액세스 정책을 만들 수 있습니다.

- 사용자 계정 이름이 Exchange, 사용자, 암호, 보안, SharePoint 또는 전역 관리자 역할이 할당된 사용자의 그룹의 구성원인 경우, 액세스를 허용하기 전에 MFA를 요구합니다.

이 정책을 사용하면 이들 관리자 역할이 할당되거나 할당이 해제될 때 MFA에 대한 개별 사용자 계정을 구성하는 대신 그룹 멤버 자격을 기반으로 MFA를 요구할 수 있습니다.

또한 특정 앱에 대해 MFA를 요구 하거나 Windows 10을 실행 하는 랩톱과 같은 준수 장치에서 로그인을 수행 하는 등 고급 기능에 조건부 액세스 정책을 사용할 수 있습니다.

Azure portal에서 Azure AD에 대 한 **보안** 창에서 조건부 액세스 정책을 구성 합니다.

![](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

다음과 같은 조건부 액세스 정책을 사용할 수 있습니다.

- Microsoft 365 Business Premium
- Microsoft 365 E3 및 E5
- Azure AD Premium P1 및 Azure AD Premium P2 라이선스 

Microsoft 365 Business Premium을 사용 하는 소규모 기업에서는 다음과 같은 단계를 통해 조건부 액세스 정책을 쉽게 사용할 수 있습니다.

1. MFA를 필요로 하는 사용자 계정을 포함할 그룹을 만듭니다.
2. **전역 관리자 정책에 대해 MFA 필요** 를 사용 하도록 설정 합니다.
3. 다음 설정을 사용 하 여 그룹 기반 조건부 액세스 정책을 만듭니다.
    - 사용자 및 그룹 > 할당: 위의 1 단계에서 그룹 이름을 지정 합니다.
    - 클라우드 앱 또는 작업을 > 할당: 모든 클라우드 앱
    - 액세스 제어 > 권한을 부여 > 액세스를 허용 하는 경우에는 multi-factor authentication이 필요 >.
4. 정책을 사용 하도록 설정 합니다.
5. 위의 1 단계에서 만든 그룹에 사용자 계정을 추가 하 고 테스트 합니다.
6. 추가 사용자 계정에 대해 MFA를 요구 하려면 1 단계에서 만든 그룹에 추가 합니다.

이 조건부 액세스 정책을 사용 하면 사용자에 게 원하는 속도로 MFA 요구 사항을 롤아웃할 수 있습니다.

기업에서는 [일반적인 조건부 액세스 정책을](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) 사용 하 여 다음 정책을 구성 해야 합니다.

- [관리자에게 MFA 요구](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [모든 사용자에 대해 MFA 요구](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [레거시 인증 차단](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

자세한 내용은 이 [조건부 액세스 개요](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)를 참조하세요.

### <a name="azure-ad-identity-protection"></a>Azure AD ID 보호

Azure AD Id 보호를 사용 하면 [로그인 위험이 중간 또는 높은 경우 MFA를 요구](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk)하는 추가 조건부 액세스 정책을 만들 수 있습니다.

다음의 경우 Azure AD Id 보호 및 위험 기반 조건부 액세스 정책을 사용할 수 있습니다.

- Microsoft 365 E5
- Azure AD Premium P2 라이선스

자세한 내용은 이 [Azure AD ID 보호 개요](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)를 참조하세요.

### <a name="mfa-for-an-individual-user-account-not-recommended"></a>개별 사용자 계정에 대 한 MFA (권장 하지 않음)

보안 기본값 또는 조건부 액세스 정책을 사용 하 여 사용자 계정 로그인에 대해 MFA를 요구 해야 합니다. 그러나 이러한 방법 중 하나를 사용할 수 없는 경우에는 모든 크기 구독에 대해 관리자 역할, 특히 전역 관리자 역할을 가진 사용자 계정에 대해 MFA를 사용 하는 것이 좋습니다. 

Microsoft 365 관리 센터의 **활성 사용자** 창에서 개별 사용자 계정에 대해 MFA를 사용 하도록 설정 합니다.

![](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

다음 번에 사용자가 로그인 하면 다음에는 MFA를 등록 하 고 추가 확인 방법을 선택 하 라는 메시지가 표시 됩니다.

### <a name="using-these-methods-together"></a>이 방법들을 함께 사용

이 표는 보안 기본값, 조건부 액세스 정책 및 사용자별 계정 설정으로 MFA를 활성화한 결과를 보여줍니다.

|| 사용 | 사용 안 함 | 보조 인증 방법 |
|:-------|:-----|:-------|:-------|
| **보안 기본값** | 조건부 액세스 정책을 사용할 수 없습니다 |   조건부 액세스 정책을 사용할 수 있습니다 | Microsoft Authenticator 앱 |
| **조건부 액세스 정책** |이 중 하나가 사용되는 경우 보안 기본값을 사용할 수 없습니다. | 상기 수단을 모두 사용하지 않도록 설정한 경우, MFA 등록 중 사용자가 지정한  | MFA 등록 중 사용자 지정 |
| **사용자별 계정 설정 (권장 하지 않음)** | 각 로그인에서 MFA를 요구 하는 보안 기본값과 조건부 액세스 정책을 재정의 합니다. | 보안 기본값 및 조건부 액세스 정책에 의해 재정의 됨 | MFA 등록 중 사용자 지정|
||||

보안 기본값을 사용 하도록 설정 하면 모든 새 사용자에 게 MFA 등록 및 다음 로그인 시 Microsoft Authenticator 앱 사용에 대 한 메시지가 표시 됩니다.

## <a name="ways-to-manage-mfa-settings"></a>MFA 설정을 관리 하는 방법

다음 두 가지 방법으로 MFA 설정을 관리할 수 있습니다.

Azure portal에서 다음 작업을 수행할 수 있습니다.

- 보안 기본값 사용 및 사용 안 함
- 조건부 액세스 정책 구성

Microsoft 365 관리 센터에서는 사용자별 및 서비스 MFA 설정을 구성할 수 있습니다.

## <a name="your-next-step"></a>다음 단계

[Microsoft 365에 대 한 MFA 설정](set-up-multi-factor-authentication.md)

