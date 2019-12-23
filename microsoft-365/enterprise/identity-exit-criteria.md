---
title: '2단계: ID 인프라 종료 조'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 구성이 ID 기반 서비스 및 인프라에 대한 Microsoft 365 Enterprise 조건을 충족하는지 확인합니다.
ms.openlocfilehash: 540d3c01ea368634cebafb2ec3dd5562fcb0b73c
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801753"
---
# <a name="phase-2-identity-infrastructure-exit-criteria"></a>2단계: ID 인프라 종료 조

![2단계-ID](./media/deploy-foundation-infrastructure/identity_icon-small.png)

ID 인프라가 다음과 같은 필수 조건 및 선택 요소에 확실히 충족하는지 확인합니다.

ID 인프라 관련 추가 권장 사항에 대해서는 [필수 구성 요소](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites)를 참조하세요.

<a name="crit-identity-global-admin"></a>
## <a name="required-your-global-administrator-accounts-are-protected"></a>필수: 전역 관리자 계정 보호 

Microsoft 365 구독을 위반할 수 있는 공격자의 자격 증명 손상을 방지하기 위해 [Office 365 전역 관리자 계정을 보호](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)해야 합니다.

이 요구 사항을 건너뛰면 전역 관리자 계정이 공격 받고 손상되기 쉽기 때문에 공격자가 시스템 전체 액세스 권한을 얻어 데이터를 수집 또는 삭제하거나 금품을 요구하기 위해 보유할 수 있습니다.

필요한 경우 [1단계](identity-create-protect-global-admins.md#identity-global-admin)를 통해 이 요구 사항을 충족할 수 있습니다.

### <a name="how-to-test"></a>테스트하는 방법

다음 단계를 사용하여 전역 관리자 계정을 보호했는지 확인합니다.

1. PowerShell 명령 프롬프트에서 다음의 Azure Active Directory PowerShell for Graph 명령을 실행하세요. 전담 전역 관리자 계정 목록만 표시됩니다.
   ```powershell
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. 1단계의 각 계정을 사용하여 Office 365에 로그인 합니다. 로그인할 때마다 Azure 다단계 인증 및 조직에서 사용 가능한 가장 강력한 형태의 보조 인증을 요구해야 합니다.

> [!Note]
> 그래프 모듈용 Azure Active Directory PowerShell 설치 및 Office 365 로그인에 대한 지침은 [Office 365 PowerShell에 연결](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)을 참조하세요.

<a name="crit-identity-pim"></a>
## <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a>선택: 요청 시 전역 관리자 역할을 할당할 수 있도록 Privileged Identity Management 설정

[Azure AD PIM(Privileged Identity Management) 구성](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)의 지침을 사용하여 Azure AD 테넌트에서 PIM을 사용하도록 설정하고 전역 관리자 계정을 적격 관리자로 구성해야 합니다.

또한 [Azure AD에서 하이브리드 및 클라우드 배포에 대한 권한 있는 액세스 보호](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)의 권장 사항을 사용하여 권한 있는 액세스를 사이버 공격자로부터 보호하는 로드맵을 마련해야 합니다.

이 옵션을 건너뛰면 전역 관리자 계정이 지속적인 온라인 공격을 받을 수 있으며, 손상된 경우 공격자가 중요한 정보를 수집 또는 삭제하거나 금품을 요구하기 위해 보유할 수 있습니다.

필요한 경우 [1단계](identity-create-protect-global-admins.md#identity-pim)를 통해 이 옵션을 충족할 수 있습니다.

<a name="crit-identity-pam"></a>
## <a name="optional-you-have-configure-privileged-access-management-in-office-365"></a>선택 사항: Office 365에 권한이 부여된 액세스 관리를 구성해야 합니다.

권한이 부여된 액세스를 사용하고 조직에서 하나 이상의 권한이 부여된 액세스 정책을 만들어내기 위해 [Office 365에서 권한이 부여된 액세스 관리 구성](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)의 정보를 사용하였습니다. 이러한 정책을 구성하고 중요한 데이터에 대한 액세스 또는 중요한 구성 설정에 대한 액세스를 위해 적기에 맞는 액세스가 활성화됩니다.

필요한 경우 [1단계](identity-create-protect-global-admins.md#identity-pam)를 통해 이 요구 사항을 충족할 수 있습니다. 

<a name="crit-password-prot"></a>
## <a name="optional-azure-ad-password-protection-is-banning-the-use-of-weak-passwords"></a>선택 사항: Azure AD 암호 보호를 사용하면 취약한 암호의 사용을 방지할 수 있습니다.

전역적으로 금지된 암호 및 선택적으로 사용자 지정 약관에 대해 [클라우드](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) 및 [온-프레미스 AD DS(Active Directory Domain Services)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises)에서 잘못된 암호 금지를 사용하도록 설정해야 합니다.

필요한 경우 [2단계](identity-secure-your-passwords.md#identity-password-prot)를 통해 이 옵션을 충족할 수 있습니다.

<a name="crit-identity-pw-reset"></a>
## <a name="optional-users-can-reset-their-own-passwords"></a>선택: 사용자가 자신의 암호를 재설정할 수 있음

[Azure AD 셀프 서비스 암호 재설정 신속 배포](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)를 사용하여 사용자에 대해 암호 재설정을 구성해야 합니다.

이 조건을 충족하지 않으면 사용자가 계정 관리자에게 암호 재설정을 요청해야 하므로 추가 IT 관리 오버헤드가 발생합니다.

필요한 경우 [2단계](identity-secure-your-passwords.md#identity-pw-reset)를 통해 이 옵션을 충족할 수 있습니다.

<a name="crit-identity-sso"></a>
## <a name="optional-users-can-sign-in-using-azure-ad-seamless-single-sign-on"></a>선택: 사용자가 Azure AD Seamless Single Sign-On을 사용하여 로그인할 수 있음

조직에서 [Azure AD Connect: Seamless Single Sign-On](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)을 사용하도록 설정하여 사용자가 Office 365와 같은 클라우드 기반 응용 프로그램에 로그인하는 방법을 간소화해야 합니다.

이 옵션을 건너뛰면 사용자가 Azure AD 테넌트를 사용하는 추가 응용 프로그램에 액세스할 때 자격 증명을 제공하라는 메시지가 표시될 수 있습니다.

필요한 경우 [2단계](identity-secure-your-passwords.md#identity-sso)를 통해 이 옵션을 충족할 수 있습니다.

<a name="crit-identity-custom-sign-in"></a>
## <a name="optional-the-office-365-sign-in-screen-is-personalized-for-your-organization"></a>선택: Office 365 로그인 화면을 조직에 맞게 개인 설

[로그인 및 액세스 패널 페이지에 회사 브랜딩을 추가](https://aka.ms/aadpaddbranding)하여 Office 365 로그인 페이지를 조직의 브랜딩을 추가해야 합니다.

이 옵션을 건너뛰면 사용자에게 일반 Office 365 로그인 화면이 표시되므로 조직의 사이트에 로그인 중인지 확신하지 못할 수 있습니다.

필요한 경우 [2단계](identity-secure-your-passwords.md#identity-custom-sign-in)를 통해 이 옵션을 충족할 수 있습니다.


<a name="crit-identity-mfa"></a>
## <a name="optional-azure-multi-factor-authentication-is-enabled-for-your-users"></a>선택 사항: 사용자에 대해 Azure 다단계 인증 사용

[Azure 다단계 인증 계획](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted) 및 [조건부 액세스 정책](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access)을 사용하여 사용자 계정에 대해 Azure MFA(Multi-Factor Authentication)를 사용하도록 설정해야 합니다.

이 옵션을 건너뛰면 사용자 계정이 사이버 공격자에 의한 자격 증명 손상에 취약해집니다. 사용자 계정의 암호가 손상되면 관리자 역할과 같은 계정의 모든 리소스 및 기능을 공격자가 사용할 수 있습니다. 따라서 공격자가 내부 문서 및 기타 데이터를 복사 또는 삭제하거나 금품을 요구하기 위해 보유할 수 있습니다.

필요한 경우 [3단계](identity-secure-user-sign-ins.md#identity-mfa)를 통해 이 옵션을 충족할 수 있습니다.

### <a name="how-to-test"></a>테스트하는 방법

1.  테스트 사용자 계정을 만들고 이 계정에 라이선스를 할당합니다. 
2.  휴대폰에 문자 메시지를 보내는 등 실제 사용자 계정에 사용 중인 추가 인증 방법으로 테스트 사용자 계정에 대해 Azure 다단계 인증을 구성합니다. 
3.  테스트 사용자 계정을 사용하여 Office 365 포털에 로그인합니다.
4.  MFA에서 추가 인증 정보를 묻고 인증에 성공하는지 확인합니다. 
5.  테스트 사용자 계정을 삭제합니다.

<a name="crit-identity-ident-prot"></a>
## <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise-microsoft-365-e5-only"></a>선택: Azure AD ID 보호를 사용하도록 설정하여 자격 증명의 노출을 방지(Microsoft 365 E5만 해당)

다음을 위해 Azure AD ID 보호를 사용하도록 설정해야 합니다.

- 잠재적인 ID 취약점 해결
- 가능한 자격 증명 손상 시도 감지
- 지속적인 의심스러운 ID 사건 조사 및 해결

이 옵션을 건너뛰면 자격 증명 손상 시도를 감지하거나 자동으로 차단할 수 없으며 ID 관련 보안 사건을 조사할 수 없습니다. 이 경우 잠재적으로 조직이 성공적인 자격 증명 손상에 취약해져 조직의 중요한 데이터가 위협에 노출될 수 있습니다.

필요한 경우 [3단계](identity-secure-user-sign-ins.md#identity-ident-prot)를 통해 이 옵션을 충족할 수 있습니다.


### <a name="how-to-test"></a>테스트하는 방법

1. 초기 암호를 사용하여 테스트 사용자 계정을 만듭니다.
2. [사용자가 Office 365에서 암호를 직접 다시 설정하도록 허용](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) 단계를 사용하여 테스트 사용자 계정의 암호를 다시 설정합니다.
3. 로그아웃했다가 재설정 암호를 사용하여 테스트 사용자 계정에 다시 로그인합니다.
4. 테스트 사용자 계정을 삭제합니다.

<a name="crit-identity-sync"></a>
## <a name="required-for-hybrid-identity-users-and-groups-are-synchronized-with-azure-ad"></a>하이브리드 ID에 필수: 사용자 및 그룹을 Azure AD와 동기화

기존 온-프레미스 AD DS(Active Directory Domain Services)가 있는 경우 Azure AD Connect를 사용하여 온-프레미스 AD DS의 사용자 계정 및 그룹을 Azure AD 테넌트에 동기화해야 합니다.

디렉터리 동기화를 사용하는 경우 사용자는 자신의 컴퓨터에 로그인하고 온-프레미스 리소스에 액세스하는 데 사용하는 것과 동일한 자격 증명을 통해 Office 365 및 다른 Microsoft 클라우드 서비스에 로그인할 수 있습니다.

필요한 경우, [4단계](identity-add-user-accounts.md#identity-sync)를 통해 이 요구 사항을 충족할 수 있습니다.

이 요구 사항을 건너뛰면 다음 두 가지 사용자 계정 및 그룹 집합을 가지게 됩니다.

- 온-프레미스 AD DS에 속해 있는 사용자 계정 및 그룹
- Azure AD 테넌트에 속해 있는 사용자 계정 및 그룹

이 상태에서는 IT 관리자 및 사용자가 두 가지 사용자 계정 및 그룹 집합을 수동으로 유지 관리해야 합니다. 이 경우 계정, 암호 및 그룹이 동기화되지 않는 상황이 발생합니다.

### <a name="how-to-test"></a>테스트 방법
온-프레미스 자격 증명과의 동기화가 올바르게 작동하는지 확인하려면 온-프레미스 자격 증명을 사용하여 Office 포털에 로그인합니다.

디렉터리 동기화가 올바르게 작동하는지 확인하려면 다음을 수행합니다.

1.  AD DS에서 새 테스트 그룹을 만듭니다.
2.  동기화 시간까지 기다립니다.
3.  Azure AD 테넌트를 확인하여 새 테스트 그룹 이름이 표시되는지 확인합니다.

<a name="crit-identity-sync-health"></a>
## <a name="optional-directory-synchronization-is-monitored"></a>선택: 디렉터리 동기화 모니터링

[동기화에 Azure AD Connect Health를 사용](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync)(암호 동기화용)하거나 [AD FS에서 Azure AD Connect Health를 사용](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs)(페더레이션된 인증용)하고 Azure AD Connect Health를 배포해야 합니다. 여기에는 다음이 포함됩니다.

- 각 온-프레미스 ID 서버에 Azure AD Connect Health 에이전트를 설치합니다.
- Azure AD Connect Health 포털을 사용하여 진행 중인 동기화의 상태를 모니터링합니다.

이 옵션을 건너뛰면 클라우드 기반 ID 인프라의 상태를 보다 정확하게 평가할 수 있습니다.

필요한 경우 [4단계](identity-add-user-accounts.md#identity-sync-health)를 통해 이 옵션을 충족할 수 있습니다.

### <a name="how-to-test"></a>테스트하는 방법
Azure AD Connect Health 포털에는 온-프레미스 도메인 컨트롤러와 진행 중인 동기화의 현재 및 올바른 상태가 표시됩니다.


<a name="crit-identity-pw-writeback"></a>
## <a name="optional-password-writeback-is-enabled-for-your-users"></a>선택: 사용자에 대해 암호 쓰기 저장 사용

[암호 쓰기 저장을 지원하는 Azure AD SSPR](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)의 지침을 사용하여 Microsoft 365 Enterprise 구독의 Azure AD 테넌트에 대해 암호 쓰기 저장을 사용하도록 설정합니다.

이 옵션을 건너뛰면 온-프레미스 네트워크에 연결되지 않은 사용자가 IT 관리자를 통해 AD DS 암호를 다시 설정하거나 잠금을 해제해야 합니다.

필요한 경우 [4단계](identity-add-user-accounts.md#identity-pw-writeback)를 통해 이 옵션을 충족할 수 있습니다.

>[!Note]
>암호 쓰기 저장은 Azure AD에서 계정 손상의 높은 위험을 감지한 경우 사용자에게 온-프레미스 암호를 변경하도록 요구하는 등 Azure AD ID 보호 기능을 최대한 활용하기 위해 필요합니다.
>

### <a name="how-to-test"></a>테스트하는 방법

Office 365에서 암호를 변경하여 암호 쓰기 저장을 테스트합니다. 계정 및 새 암호를 사용하여 온-프레미스 AD DS 리소스에 액세스할 수 있어야 합니다.

1. 온-프레미스 AD DS에서 테스트 사용자 계정을 만들고 디렉터리 동기화가 발생하도록 허용한 다음 Office 365 관리 센터에서 Microsoft 365 Enterprise 라이선스를 부여합니다.
2. 온-프레미스 AD DS 도메인에 가입된 원격 컴퓨터에서 테스트 사용자 계정의 자격 증명을 사용하여 컴퓨터 및 Office 포털에 로그인합니다.
3. **설정 > Office 365 설정 > 암호 > 암호 변경**을 선택합니다.
4. 현재 암호와 새 암호를 차례로 입력하고 확인합니다.
5. Office 포털과 원격 컴퓨터에서 로그아웃한 다음 테스트 사용자 계정과 새 암호를 사용하여 컴퓨터에 로그인합니다. 이는 Azure AD 테넌트를 사용하여 온-프레미스 AD DS 사용자 계정의 암호를 변경할 수 있음을 입증합니다.

### <a name="how-to-test"></a>테스트하는 방법

사용자 계정 이름과 Azure 다단계 인증을 사용하 여 Office 365 포털에 로그인합니다. 로그인 페이지에서 사용자 지정 브랜드 요소를 확인할 수 있습니다.


<a name="crit-identity-self-service-groups"></a>
## <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-office-365-groups"></a>선택: 특정 Azure AD 보안 및 Office 365 그룹에 대해 셀프 서비스 관리 사용

그룹이 셀프 서비스 관리에 적합한지 확인하고, 해당 소유자에게 그룹 관리 워크플로 및 책임을 알리고, 그룹에 대해 [Azure AD에서 셀프 서비스 관리를 설정](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management)해야 합니다.

이 옵션을 건너뛰면 모든 Azure AD 그룹 관리 작업을 IT 관리자가 수행해야 합니다.

필요한 경우 [5단계](identity-use-group-management.md#identity-self-service-groups)를 통해 이 옵션을 충족할 수 있습니다.

### <a name="how-to-test"></a>테스트하는 방법
1.  Azure Portal을 통해 Azure AD에서 테스트 사용자 계정을 만듭니다.
2.  테스트 사용자 계정으로 로그인하여 테스트 Azure AD 보안 그룹을 만듭니다.
3.  로그아웃했다가 IT 관리자 계정으로 다시 로그인합니다.
4.  테스트 사용자 계정에 대한 셀프 서비스 관리를 위해 테스트 보안 그룹을 구성합니다.
5.  로그아웃했다가 테스트 사용자 계정으로 다시 로그인합니다.
6.  Azure Portal을 사용하여 테스트 보안 그룹에 구성원을 추가합니다.
7.  테스트 보안 그룹과 테스트 사용자 계정을 삭제합니다.

<a name="crit-identity-dyn-groups"></a>
## <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a>선택: 사용자 계정 특성에 따라 사용자 계정을 그룹에 자동으로 추가하는 동적 그룹 구성원 설정

Azure AD 동적 그룹 집합을 확인하고 [Azure Active Directory의 특성 기반 동적 그룹 구성원](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)의 지침을 사용하여 그룹과 함께 사용자 계정 특성 및 그룹 구성원 값 집합을 결정하는 규칙을 만들어야 합니다.

이 옵션을 건너뛰면 새 계정이 추가되거나 시간이 지남에 따라 사용자 계정 특성이 변경될 때 그룹 구성원을 수동으로 구성해야 합니다. 예를 들어 누군가 영업 부서에서 회계 부서로 이동한 경우 다음을 수행해야 합니다.

- 해당 사용자 계정에 대한 Department 특성 값 업데이트
- 영업 그룹에서 해당 사용자를 수동으로 제거
- 회계 그룹에 해당 사용자를 수동으로 추가

영업 및 회계 그룹이 동적인 경우 사용자 계정의 부서 값만 변경해야 합니다.

필요한 경우 [5단계](identity-use-group-management.md#identity-dyn-groups)를 통해 이 옵션을 충족할 수 있습니다.

### <a name="how-to-test"></a>테스트하는 방법

1. Azure Portal을 통해 Azure AD에서 테스트 동적 그룹을 만들고 Department = "test1"에 대한 규칙을 구성합니다.
2. Azure AD에서 테스트 사용자 계정을 만들고 Department 속성을 "test1"로 설정합니다.
3. 사용자 계정의 속성을 검사하여 테스트 동적 그룹의 구성원이 변경되었는지 확인합니다.
4. 테스트 사용자 계정에 대한 Department 속성 값을 "test2"로 변경합니다.
5. 사용자 계정의 속성을 검사하여 더 이상 테스트 동적 그룹의 구성원이 아닌지 확인합니다.
6. 테스트 동적 그룹과 테스트 사용자 계정을 삭제합니다.

<a name="crit-identity-group-license"></a>
## <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a>선택: 그룹 구성원을 기반으로 사용자 계정에 라이선스를 자동으로 할당하고 제거하는 그룹 기반 라이선싱

Microsoft 365 Enterprise 라이선스가 자동으로 할당되거나 할당 해제되도록 적절한 Azure AD 보안 그룹에 대해 [그룹 기반 라이선싱을 사용하도록 설정](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)해야 합니다.

이 옵션을 건너뛰면 다음 작업을 수동으로 수행해야 합니다.

- 액세스 권한을 부여하려는 새 사용자에게 라이선스를 할당합니다.
- 더 이상 조직과 관련이 없거나 액세스 권한이 없는 사용자로부터 라이선스를 할당 해제합니다.

필요한 경우 [5단계](identity-use-group-management.md#identity-group-license)를 통해 이 옵션을 충족할 수 있습니다.

### <a name="how-to-test"></a>테스트하는 방법

1. Azure Portal을 통해 Azure AD에서 테스트 보안 그룹을 만들고 Microsoft 365 Enterprise 라이선스를 할당하도록 그룹 기반 라이선싱을 구성합니다.
2. Azure AD에서 테스트 사용자 계정을 만들고 테스트 보안 그룹에 추가합니다.
3. Microsoft 365 관리 센터에서 사용자 계정의 속성을 검사하여 Microsoft 365 Enterprise 라이선스가 할당되었는지 확인합니다.
4. 테스트 보안 그룹에서 테스트 사용자 계정을 제거합니다.
5. 사용자 계정의 속성을 검사하여 Microsoft 365 Enterprise 라이선스가 더 이상 할당되지 않았는지 확인합니다.
6. 테스트 보안 그룹과 테스트 사용자 계정을 삭제합니다.


<a name="crit-identity-access-reviews"></a>
## <a name="optional-access-reviews-configured-and-being-used-to-monitor-access"></a>선택: 액세스 검토를 구성하고 액세스를 모니터링하는 데 사용

다음 문서를 사용하여 그룹 구성원 자격, 엔터프라이즈 애플리케이션에 대한 액세스 및 역할 할당을 모니터링하도록 다양한 유형의 액세스 검토를 구성해야 합니다.

- [그룹 및 앱](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [Azure AD 역할](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Azure 리소스 역할](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

필요한 경우 [6단계](identity-configure-identity-governance.md#identity-access-reviews)를 통해 이 옵션을 충족할 수 있습니다.


## <a name="results-and-next-steps"></a>결과 및 다음 단계

Microsoft 365 클라우드의 ID 인프라에서는 강력한 인증, 보호된 관리자 계정, 간소화된 사용자 액세스 및 관리를 사용합니다.

|||
|:-------|:-----|
|![3단계: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)| Microsoft 365 Enterprise의 종단 간 배포 단계를 수행 중인 경우 다음 단계는 [Windows 10 Enterprise](windows10-infrastructure.md)입니다. |

