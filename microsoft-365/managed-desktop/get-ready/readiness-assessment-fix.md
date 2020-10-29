---
title: 준비 상태 평가 도구에서 발견 된 문제 해결
description: 도구에서 발견 되는 각 문제에 대해 수행할 세부 작업
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a6dec9473ee632b74bb79e50156cedff53a3cba3
ms.sourcegitcommit: fa26da0be667d4be0121c52b05488dc76c5d626c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2020
ms.locfileid: "48795120"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>준비 상태 평가 도구에서 발견 된 문제 해결

각 검사에 대해이 도구는 다음과 같은 네 가지 가능한 결과 중 하나를 보고 합니다.


|결과  |의미  |
|---------|---------|
|맞춤형     | 등록을 완료 하기 전에 작업을 수행할 필요가 없습니다.        |
|조언    | 등록 및 사용자를 위한 최상의 환경을 위해서는이 도구 또는이 문서에 나와 있는 단계를 따르세요. 등록을 완료할 *수* 있지만 첫 번째 장치를 배포 하기 전에 이러한 문제를 해결 해야 합니다.        |
|준비되지 않음 | *이러한 문제를 해결 하지 않으면 등록에 실패 합니다.* 도구 또는이 문서의 단계에 따라 문제를 해결 합니다.        |
|오류 | 사용 중인 Azure 활성 디렉터 (AD) 역할에이 검사를 실행할 수 있는 충분 한 권한이 없습니다. |

## <a name="microsoft-intune-settings"></a>Microsoft Intune 설정

### <a name="autopilot-deployment-profile"></a>Autopilot 배포 프로필

할당 된 또는 동적 그룹을 대상으로 하는 기존 Autopilot 프로필은 Microsoft Managed Desktop에서 사용 하지 않아야 합니다. Microsoft Managed Desktop은 Autopilot를 사용 하 여 새 장치를 프로 비전 합니다.

**준비되지 않음**

모든 장치에 할당 된 Autopilot 프로필이 있어야 합니다. 자세한 단계는 [Windows Autopilot을 사용 하 여 Intune에서 windows 장치 등록](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)을 참조 하십시오. Microsoft Managed Desktop 등록 후에는 Autopilot 정책을 설정 하 여 **최신 작업 공간 장치 (All** Azure AD 그룹)를 제외 합니다.

**조언**

Autopilot 프로필이 등록 시 만들 Microsoft Managed Desktop devices를 포함 하지 않는 할당 된 또는 동적 Azure AD 그룹을 대상으로 하는지 확인 합니다. 자세한 단계는 [Windows Autopilot을 사용 하 여 Intune에서 windows 장치 등록](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)을 참조 하십시오. Microsoft Managed Desktop 등록 후에는 Autopilot 정책을 설정 하 여 **최신 작업 공간 장치 (All** Azure AD 그룹)를 제외 합니다.


### <a name="certificate-connectors"></a>인증서 커넥터

Microsoft Managed Desktop에서 등록 하려는 장치에서 사용 하는 인증서 커넥터가 있으면 커넥터에 오류가 발생 하지 않습니다. 다음 권고 중 하나만 상황에 맞게 적용 되므로 신중 하 게 확인 해야 합니다.

**조언**

인증서 커넥터가 없습니다. 커넥터가 필요 하지 않을 수 있지만 Microsoft Managed Desktop 장치에 대 한 네트워크 연결에 대 한 몇 가지 필요 여부를 평가 해야 합니다. 자세한 내용은 [Microsoft Managed Desktop에 대 한 인증서 및 네트워크 프로필 준비](certs-wifi-lan.md)를 참조 하세요.

**조언**

하나 이상의 인증서 커넥터에 오류가 있습니다. Microsoft Managed Desktop 장치에 연결 하기 위해이 커넥터가 필요한 경우 오류를 해결 해야 합니다. 자세한 내용은 [Microsoft Managed Desktop에 대 한 인증서 및 네트워크 프로필 준비](certs-wifi-lan.md)를 참조 하세요.


**조언**

하나 이상의 인증서 커넥터가 있고 오류가 보고 되지 않습니다. 그러나 Microsoft Managed Desktop 장치에 대 한 커넥터를 다시 사용 하려면 프로필을 만들어야 할 수 있습니다. 자세한 내용은 [Microsoft Managed Desktop에 대 한 인증서 및 네트워크 프로필 준비](certs-wifi-lan.md)를 참조 하세요.


### <a name="conditional-access-policies"></a>조건부 액세스 정책

Azure AD 조직의 조건부 액세스 정책은 Microsoft 관리 데스크톱 사용자를 대상으로 하지 않아야 합니다.

**준비되지 않음**

모든 사용자를 대상으로 하는 하나 이상의 조건부 액세스 정책이 있어야 합니다. 등록할 때 생성 되는 Microsoft Managed Desktop service 계정의 Azure AD 그룹을 포함 하지 않는 특정 Azure AD 그룹을 대상으로 하도록 정책을 다시 설정 합니다. 단계에 대 한 자세한 내용은 [조건부 액세스: 사용자 및 그룹](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)을 참조 하십시오.

**조언**

모든 조건부 액세스 정책에서 **최신 직장의 작업 공간 서비스 계정** Azure AD 그룹을 제외 했는지 확인 합니다. 단계에 대 한 자세한 내용은 [조건부 액세스 조정을](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access)참조 하십시오. **최신 작업 공간 서비스 계정** Azure AD 그룹은 등록할 때 서비스를 위해 만드는 동적 그룹입니다. 등록 한 후에는이 그룹을 제외 하려면 다시 방문 해야 합니다. 이러한 서비스 계정에 대 한 자세한 내용은 [표준 운영 절차](../service-description/operations-and-monitoring.md#standard-operating-procedures)를 참조 하세요.

**오류**

Intune 관리자 역할에는이 검사에 대 한 충분 한 사용 권한이 없습니다. 또한이 검사를 실행 하려면 이러한 모든 Azure AD 역할을 할당 받아야 합니다.

- 보안 읽기 권한자
- 보안 관리자
- 조건부 액세스 관리자
- 전역 읽기 권한자
- 장치 관리자


### <a name="device-compliance-policies"></a>장치 준수 정책

Azure AD 조직의 Intune 장치 준수 정책은 Microsoft Managed Desktop 사용자를 대상으로 하지 않아야 합니다.

**준비되지 않음**

모든 사용자를 대상으로 하는 준수 정책이 하나 이상 있어야 합니다. Microsoft Managed Desktop users를 포함 하지 않는 특정 Azure AD 그룹을 대상으로 하도록 정책을 다시 설정 합니다. 자세한 단계는 [Microsoft Intune에서 준수 정책 만들기](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)를 참조 하세요.

**조언**

준수 정책에 Microsoft Managed Desktop users가 포함 되어 있지 않은지 확인 합니다. 자세한 단계는 [Microsoft Intune에서 준수 정책 만들기](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)를 참조 하세요.



### <a name="device-configuration-policies"></a>장치 구성 정책

Azure AD 조직의 Intune 장치 구성 정책은 Microsoft 관리 데스크톱 장치 또는 사용자를 대상으로 하지 않아야 합니다.

**준비되지 않음**

모든 사용자, 모든 장치 또는 둘 다를 대상으로 하는 구성 정책이 하나 이상 있어야 합니다. Microsoft Managed Desktop 장치를 포함 하지 않는 특정 Azure AD 그룹을 대상으로 하도록 정책을 다시 설정 합니다. 자세한 단계는 [Microsoft Intune에서 준수 정책 만들기](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)를 참조 하세요.

**조언**

준수 정책에 Microsoft 관리 되는 데스크톱 장치 또는 사용자가 포함 되어 있지 않은지 확인 합니다. 자세한 단계는 [Microsoft Intune에서 준수 정책 만들기](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)를 참조 하세요.



### <a name="device-type-restrictions"></a>장치 유형 제한

Microsoft Managed Desktop 장치는 Intune에서 등록할 수 있어야 합니다.

**준비되지 않음**

[등록 제한 설정](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) 의 단계에 따라 설정을 **허용** 으로 변경 합니다.


### <a name="enrollment-status-page"></a>등록 상태 페이지

현재 ESP (등록 상태 페이지)를 사용 하도록 설정 합니다. 이 기능의 공개 미리 보기에 참여 하는 경우에는이 항목을 무시 해도 됩니다. 자세한 내용은 [Autopilot 및 등록 상태 페이지를 사용 하 여 첫 실행 환경을](../get-started/esp-first-run.md)참조 하세요.

**준비되지 않음**

**앱 및 프로필 구성 진행률을 표시** 하도록 ESP 기본 프로필을 설정 해야 합니다. [등록 상태 설정 페이지](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)의 단계를 수행 하 여이 설정을 사용 하지 않도록 설정 합니다.

**조언**

**앱 및 프로필 구성 진행률** 설정이 있는 모든 프로필이 Microsoft Managed Desktop 장치를 포함 하는 Azure AD 그룹에 할당 되어 있지 않은지 확인 합니다. 자세한 내용은 [등록 상태 설정 페이지](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)를 참조 하세요.

### <a name="intune-enrollment"></a>Intune 등록

Azure AD 조직의 Windows 10 장치는 Intune에서 자동으로 등록 해야 합니다.

**준비되지 않음**

Azure AD 조직의 사용자는 Microsoft Intune에 자동으로 등록 되지 않습니다. MDM 사용자 범위를 **일부** 또는 **모두** 로 변경 합니다. **일부** 를 선택 하는 경우 등록 후에 다시 돌아와서 **그룹** 에 대 한 **최신 작업 회사-All** Azure AD 그룹을 선택 합니다.


### <a name="microsoft-store-for-business"></a>비즈니스용 Microsoft Store

회사 포털을 다운로드 하 여 Microsoft Project 및 Microsoft Visio와 같은 일부 앱을 배포할 수 있도록 Microsoft Store for Business를 사용 하 고 있습니다.

**준비되지 않음**

비즈니스용 Microsoft Store가 사용 하도록 설정 되지 않았거나 Intune과 동기화 되지 않습니다. 자세한 내용은 microsoft [intune을 사용 하 여 비즈니스용 Microsoft 스토어에서 구입한 볼륨 구입 앱을 관리](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) 하 고 [장치에 Intune 회사 포털을 설치](../get-started/company-portal.md)하는 방법을 참조 하세요.

### <a name="multi-factor-authentication"></a>다단계 인증

Microsoft Managed Desktop 서비스 계정에는 실수로 다단계 인증을 적용 해서는 안 됩니다.


**준비되지 않음**

일부 MFA (multi-factor authentication) 정책이 모든 사용자에 게 할당 된 조건부 액세스 정책에 대해 "필수"로 설정 되어 있어야 합니다. Microsoft Managed Desktop 장치를 포함 하지 않는 특정 Azure AD 그룹을 대상으로 하는 할당을 사용 하도록 정책을 변경 합니다. 자세한 내용은 [조건부 액세스 정책](#conditional-access-policies) 및 [조건부 액세스: 모든 사용자에 대해 MFA 필요](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)를 참조 하세요.

**조언**

MFA가 필요한 조건부 액세스 정책이 **최신 직장의 모든** Azure AD 그룹을 제외 하는지 확인 합니다. 자세한 내용은 [조건부 액세스 정책](#conditional-access-policies) 및 [조건부 액세스: 모든 사용자에 대해 MFA 필요](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)를 참조 하세요. **최신 작업 회사-All** Azure AD 그룹은 Microsoft Managed Desktop에 등록할 때 작성 하는 동적 그룹으로, 등록 후에이 그룹을 제외 하려면 다시 방문 해야 합니다.

**오류**

Intune 관리자 역할에는이 검사에 대 한 충분 한 사용 권한이 없습니다. 또한이 검사를 실행 하려면 이러한 모든 Azure AD 역할을 할당 받아야 합니다.

- 보안 읽기 권한자
- 보안 관리자
- 조건부 액세스 관리자
- 전역 읽기 권한자
- 장치 관리자


### <a name="powershell-scripts"></a>PowerShell 스크립트

Microsoft Managed Desktop 장치를 대상으로 하는 방식으로 Windows PowerShell 스크립트를 할당할 수 없습니다.  

**조언**

Azure AD 조직의 Windows PowerShell 스크립트에서 어떤 Microsoft 데스크톱 장치나 사용자도 관리 하지 않는지 확인 합니다. 자세한 내용은 [Intune에서 Windows 10 장치에서 PowerShell 스크립트 사용](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)을 참조 하세요.

### <a name="region"></a>지역

사용자의 지역을 Microsoft Managed Desktop에서 지원 해야 합니다.

**준비되지 않음**

현재 Azure AD 조직 지역이 Microsoft Managed Desktop에서 지원 되지 않습니다. 자세한 내용은 [Microsoft Managed Desktop 지원 지역 및 언어](../service-description/regions-languages.md)를 참조 하세요.

**조언**

Azure AD 조직이 있는 하나 이상의 국가는 Microsoft Managed Desktop에서 지원 되지 않습니다. 자세한 내용은 [Microsoft Managed Desktop 지원 지역 및 언어](../service-description/regions-languages.md)를 참조 하세요.


### <a name="security-baselines"></a>보안 기준

보안 기본 정책은 Microsoft 관리 되는 데스크톱 장치를 대상으로 지정 해서는 안 됩니다.

**준비되지 않음**

모든 사용자, 모든 장치 또는 둘 다를 대상으로 하는 보안 기준 프로필을 보유 하 고 있습니다. Microsoft Managed Desktop 장치를 포함 하지 않는 특정 Azure AD 그룹을 대상으로 하는 할당을 사용 하도록 정책을 변경 합니다. 자세한 단계는 [security 기준선이 Use To Windows 10 devices In Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines)을 참조 하십시오.

**조언**

Microsoft Managed Desktop 장치를 제외 하는 보안 기본 정책이 있는지 확인 합니다. 자세한 단계는 [security 기준선이 Use To Windows 10 devices In Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines)을 참조 하십시오. **최신 작업 공간 장치-모든** Azure AD 그룹은 Microsoft Managed Desktop에 등록할 때 만든 동적 그룹으로, 등록 후에이 그룹을 제외 하려면 다시 받아야 합니다.


### <a name="windows-apps"></a>Windows 앱

Microsoft Managed Desktop 사용자에 게 부여할 앱을 검토 합니다.

**조언**

Microsoft Managed Desktop 사용자에 게 부여할 앱의 인벤토리를 준비 해야 합니다. Intune을 통해 이러한 앱을 배포할 수 있는지 확인 합니다. 자세한 내용은 [Microsoft Managed Desktop의 앱](apps.md)을 참조 하세요.

Microsoft 계정 담당자에 게 문의 하 여 Intune으로 마이그레이션하거나, 조정이 필요한 앱을 확인할 수 있습니다.


### <a name="windows-hello-for-business"></a>비즈니스용 Windows Hello

Microsoft Managed Desktop을 사용 하려면 비즈니스용 Windows Hello가 설정 되어 있어야 합니다.

**준비되지 않음**

비즈니스용 Windows Hello가 사용 하지 않도록 설정 되었습니다. [비즈니스용 Windows Hello 정책 만들기](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy) 의 단계를 수행 하 여이 기능을 사용 하도록 설정 합니다.

**조언**

비즈니스용 Windows Hello가 설정 되지 않았습니다. [비즈니스용 Windows Hello 정책 만들기](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)의 단계를 수행 하 여이 기능을 사용 하도록 설정 합니다.


### <a name="windows-10-update-rings"></a>Windows 10 업데이트 링

Intune의 "Windows 10 업데이트 링" 정책은 Microsoft Managed Desktop 장치를 대상으로 하지 않아야 합니다.

**준비되지 않음**

모든 장치, 모든 사용자 또는 둘 다를 대상으로 하는 "업데이트 링" 정책이 있습니다. Microsoft Managed Desktop 장치를 포함 하지 않는 특정 Azure AD 그룹을 대상으로 하는 할당을 사용 하도록 정책을 변경 합니다. 자세한 단계는 [Intune에서 Windows 10 소프트웨어 업데이트 관리](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)를 참조 하세요.

**조언**

업데이트 링 정책에서 **최신 직장의 작업 공간-All** Azure AD 그룹을 제외 했는지 확인 합니다. 자세한 단계는 [Intune에서 Windows 10 소프트웨어 업데이트 관리](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)를 참조 하세요. **최신 작업 공간 장치-모든** Azure AD 그룹은 Microsoft Managed Desktop에 등록할 때 만든 동적 그룹으로, 등록 후에이 그룹을 제외 하려면 다시 받아야 합니다.


## <a name="azure-active-directory-settings"></a>Azure Active Directory 설정


### <a name="ad-hoc-subscriptions"></a>임시 구독

"False"로 설정 된 경우 엔터프라이즈 상태 로밍이 제대로 작동 하지 않을 수 있는 설정을 확인 하는 방법을 제안 합니다.

**조언**

**AllowAdHocSubscriptions** 이 **True** 로 설정 되어 있는지 확인 합니다. 그렇지 않으면 엔터프라이즈 상태 로밍이 작동 하지 않을 수 있습니다. 자세한 내용은 [set-msolcompanysettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)를 참조 하십시오.


### <a name="enterprise-state-roaming"></a>Enterprise State Roaming

엔터프라이즈 상태 로밍을 사용 하도록 설정 해야 합니다.

**조언**

**모든** 또는 **선택한** 그룹에 대해 엔터프라이즈 상태 로밍을 사용 하도록 설정 되어 있는지 확인 합니다. 자세한 내용은 [Azure Active Directory에서 엔터프라이즈 상태 로밍을 사용 하도록 설정을](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)참조 하십시오.

### <a name="licenses"></a>라이선스

Microsoft Managed Desktop을 사용 하려면 많은 라이선스가 필요 합니다.

**준비 되지 않음**

Microsoft Managed Desktop을 사용 하는 데 필요한 라이선스가 모두 없습니다. 자세한 내용은 [Microsoft Managed Desktop 기술](../intro/technologies.md) 및 [라이선스에 대 한 추가](prerequisites.md#more-about-licenses)정보를 참조 하세요.


### <a name="security-account-names"></a>보안 계정 이름

특정 보안 계정 이름이 Microsoft Managed Desktop에서 만든 이름과 충돌할 수 있습니다.

**준비되지 않음**

Microsoft Managed Desktop에서 만든 계정 이름과 충돌 하는 계정이 하나 이상 있어야 합니다. Microsoft 계정 담당자와 협력 하 여 이러한 계정 이름을 제외 합니다.


### <a name="security-administrator-roles"></a>보안 관리자 역할

특정 보안 역할을 가진 사용자에 게는 끝점에 대해 Microsoft Defender에서 할당 해야 합니다.

**조언**

Azure AD 조직에 이러한 역할이 할당 되어 있는 경우이 역할에도 Microsoft Defender for Endpoint에 할당 된 이러한 역할이 있는지 확인 합니다. 그렇지 않으면 이러한 역할을 가진 관리자가 관리자 포털에 액세스할 수 없습니다.

- 보안 읽기 권한자
- 보안 운영자
- 전역 읽기 권한자

자세한 내용은 [역할 기반 액세스 제어에 대 한 역할 만들기 및 관리](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)를 참조 하세요.


### <a name="security-default"></a>보안 기본값

Azure Active Directory의 보안 기본값을 설정 하면 Microsoft Managed Desktop에서 장치를 관리할 수 없습니다.

**준비되지 않음**

보안 기본값이 설정 되어 있어야 합니다. 보안 기본값을 해제 하 고 조건부 액세스 정책을 설정 합니다. 자세한 내용은 [일반 조건부 액세스 정책](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)를 참조 하세요.

### <a name="self-service-password-reset"></a>셀프 서비스 암호 재설정

셀프 서비스 암호 재설정 (SSPR)을 사용 하도록 설정 해야 합니다.

**준비되지 않음**

모든 사용자에 대해 SSPR를 사용 하도록 설정 해야 합니다. 그렇지 않으면 Microsoft Managed Desktop service 계정이 작동할 수 없습니다. 자세한 내용은 [Tutorial: 사용자가 Azure Active Directory 셀프 서비스 암호 재설정을 사용 하 여 계정의 잠금을 해제 하거나 암호를 재설정할 수 있도록](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)합니다 .를 참조 하세요.

**조언**

SSPR **Selected** 설정에 Microsoft Managed Desktop devices가 포함 되어 있는지 확인 합니다.

**오류**

Intune 관리자 역할에는이 검사에 대 한 충분 한 사용 권한이 없습니다. 또한이 검사를 실행 하려면 보고서 판독기 Azure AD 역할이 할당 되어 있어야 합니다.


### <a name="standard-user-role"></a>표준 사용자 역할

Microsoft Managed Desktop 사용자는 로컬 관리자 권한이 없는 표준 사용자 여야 합니다. Microsoft Managed Desktop 장치를 시작할 때 표준 사용자 역할이 할당 될 예정입니다.

**조언**

Microsoft Managed Desktop 사용자에 게 등록 하기 전에 로컬 관리자 권한이 없어야 합니다.

## <a name="microsoft-365-apps-for-enterprise"></a>엔터프라이즈용 Microsoft 365 앱

### <a name="onedrive-for-business"></a>비즈니스용 OneDrive

**특정 도메인에 가입 된 pc 에서만 동기화 허용** 설정은 Microsoft Managed Desktop과 충돌 합니다.

**조언**

**특정 도메인에 가입 된 pc 에서만 동기화 허용** 설정을 사용 하 고 있습니다. 이 설정은 Microsoft Managed Desktop에서는 작동 하지 않습니다. 이 설정을 사용 하지 않고 비즈니스용 OneDrive에서 조건부 액세스 정책을 사용 하도록 설정 합니다. 도움말을 보려면 [조건부 액세스 배포 계획을](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) 참조 하세요.

