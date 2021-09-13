---
title: 준비 평가 도구에서 발견한 문제 해결
description: 도구에서 찾을 수 있는 각 문제별로 수행할 세부 작업
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: f3ccb47c2facffed0a259b4807f8155b4c87cb70
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215542"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>준비 평가 도구에서 발견한 문제 해결

각 검사에 대해 도구는 다음 네 가지 결과 중 하나를 보고합니다.


|결과  |의미  |
|---------|---------|
|준비     | 등록을 완료하기 전에 필요한 작업은 없습니다.        |
|권고    | 등록과 사용자에게 최상의 환경을 제공하려면 도구 또는 이 문서의 단계를 따르세요. *등록을* 완료할 수 있지만 첫 번째 장치를 배포하기 전에 이러한 문제를 해결해야 합니다.        |
|준비되지 않음 | *이러한 문제를 해결하지 않는 경우 등록이 실패합니다.* 도구 또는 이 문서의 단계에 따라 문제를 해결합니다.        |
|오류 | 사용 Azure Active Directory(AD) 역할에 이 검사를 실행할 수 있는 권한이 없습니다. |

> [!NOTE]
> 이 도구에서 보고한 결과에는 설정이 실행된 특정 시점에만 설정의 상태가 반영됩니다. 나중에 Microsoft Intune, Azure Active Directory 또는 Microsoft 365 변경하면 "준비되지 않은" 항목이 될 수 있습니다. 정책 Microsoft Managed Desktop 문제를 방지하려면 정책을 변경하기 전에 이 문서에 설명된 특정 설정을 확인합니다.

## <a name="microsoft-intune-settings"></a>Microsoft Intune 설정

Intune 설정은 Microsoft Endpoint Manager [있습니다.](https://endpoint.microsoft.com)

### <a name="autopilot-deployment-profile"></a>Autopilot 배포 프로필

장치와 함께 할당되거나 동적 그룹을 대상으로 하는 기존 Autopilot 프로필이 Microsoft Managed Desktop 없습니다. Microsoft Managed Desktop Autopilot을 사용하여 새 장치를 프로비전합니다.

**준비되지 않음**

모든 장치에 할당된 Autopilot 프로필이 있습니다. 단계에 대한 자세한 [내용은 Autopilot Windows 사용하여 Intune에 Windows 등록을 참조하세요.](/mem/autopilot/enrollment-autopilot) 등록 Microsoft Managed Desktop 후 Autopilot 정책을 설정하여 최신 작업 공간 장치 **-All** Azure AD 그룹을 제외합니다.

**권고**

Autopilot 프로필이 디바이스를 포함하지 않는 할당된 또는 동적 Azure AD 그룹을 Microsoft Managed Desktop 합니다. 단계에 대한 자세한 [내용은 Autopilot Windows 사용하여 Intune에 Windows 등록을 참조하세요.](/mem/autopilot/enrollment-autopilot) 등록 Microsoft Managed Desktop 후 Autopilot 프로필을 설정하여 최신 작업 공간 장치 **-All** Azure AD 그룹을 제외합니다.


### <a name="certificate-connectors"></a>인증서 커넥터

등록하려는 장치에서 사용할 인증서 커넥터가 있는 Microsoft Managed Desktop 커넥터에 오류가 없는 것입니다. 다음 권고 중 하나만 상황에 적용될 것이기 때문에 주의 깊게 검토하십시오.

**권고**

인증서 커넥터가 없습니다. 커넥터가 필요하지 않을 수도 있지만, 커넥터를 사용할 때 네트워크 연결에 일부가 필요한지 여부를 평가해야 Microsoft Managed Desktop 있습니다. 자세한 내용은 [Prepare certificates and network profiles for Microsoft Managed Desktop.](certs-wifi-lan.md)

**권고**

하나 이상의 인증서 커넥터에 오류가 있습니다. 모든 디바이스에 인증서를 제공하기 위해 이 커넥터가 Microsoft Managed Desktop 해결해야 합니다. 자세한 내용은 [Prepare certificates and network profiles for Microsoft Managed Desktop.](certs-wifi-lan.md)


**권고**

인증서 커넥터가 하나 이상 있으며 오류가 보고되지 않습니다. 그러나 배포를 준비할 때 장치용 커넥터를 다시 사용할 프로필을 만들어야 Microsoft Managed Desktop 있습니다. 자세한 내용은 [Prepare certificates and network profiles for Microsoft Managed Desktop.](certs-wifi-lan.md)

### <a name="company-portal"></a>회사 포털

Microsoft Managed Desktop 장치를 사용하려면 IT Intune 회사 포털 장치를 설치해야 Microsoft Managed Desktop 합니다. 

**준비되지 않음**

사용자에 대해 회사 포털 설치되지 않았습니다. Intune과 회사 포털 동기화를 강제로 비즈니스용 Microsoft Store. 자세한 내용은 장치에 Intune 회사 포털 [설치를 참조하세요.](../get-started/company-portal.md)


### <a name="conditional-access-policies"></a>조건부 액세스 정책

조건부 액세스 정책으로 인해 Microsoft Managed Desktop Azure AD에서 Azure AD 조직(테넌트)을 관리할 수 없습니다.

**준비되지 않음**

모든 사용자를 대상으로 하는 조건부 액세스 정책이 하나 이상 있습니다. 등록하는 동안 관련 조건부 액세스 Microsoft Managed Desktop 서비스 계정을 제외하고 이러한 계정에 대한 액세스를 제한하기 위해 새 조건부 액세스 정책을 적용합니다. 등록 후 2013에서 Microsoft Managed Desktop 조건부 액세스 정책을 검토할 Microsoft Endpoint Manager. 이러한 서비스 계정에 대한 자세한 내용은 표준 운영 [절차 를 참조합니다.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**권고**

사용자가 Microsoft Managed Desktop 서비스를 관리하지 못하게 할 수 있는 조건부 액세스 Microsoft Managed Desktop 있습니다. 등록하는 동안 관련 조건부 액세스 Microsoft Managed Desktop 서비스 계정을 제외하고 이러한 계정에 대한 액세스를 제한하기 위해 새 조건부 액세스 정책을 적용합니다. 이러한 서비스 계정에 대한 자세한 내용은 표준 운영 [절차 를 참조합니다.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**오류**

Intune 관리자 역할에는 이 검사에 대한 충분한 권한이 없습니다. 이 검사를 실행하려면 다음 Azure AD 역할도 할당해야 합니다.

- 보안 읽기 권한자
- 보안 관리자
- 조건부 액세스 관리자
- 전역 읽기 권한자
- 장치 관리자


### <a name="device-compliance-policies"></a>장치 준수 정책

Azure AD 조직의 Intune 장치 준수 정책은 디바이스에 영향을 Microsoft Managed Desktop 있습니다.

**권고**

모든 사용자를 적용하는 규정 준수 정책이 하나 이상 있습니다. Microsoft Managed Desktop 장치에 적용되는 준수 정책도 Microsoft Managed Desktop 포함됩니다. 조직에서 만든 모든 준수 정책을 검토하여 Microsoft Managed Desktop 장치에 적용하여 충돌이 없는지 검토합니다. 단계에 대한 자세한 내용은 [에서 준수](/mem/intune/protect/create-compliance-policy)정책 Microsoft Intune.



### <a name="device-configuration-profiles"></a>장치 구성 프로필

Azure AD 조직의 Intune 장치 구성 프로필은 Microsoft Manage Desktop 장치 또는 사용자를 대상으로 지정하지 말아야 합니다.

**준비되지 않음**

모든 사용자, 모든 장치 또는 둘 다에 적용되는 구성 프로필이 하나 이상 있습니다. 프로필을 다시 설정하여 모든 디바이스를 포함하지 않는 특정 Azure AD 그룹에 Microsoft Managed Desktop. 단계는 에서 사용자 지정 설정을 사용하여 프로필 [Microsoft Intune.](/mem/intune/configuration/custom-settings-configure)

**권고**

모든 구성 정책에 장치 또는 사용자를 포함하지 Microsoft Managed Desktop 합니다. 단계는 에서 사용자 지정 설정을 사용하여 프로필 [Microsoft Intune.](/mem/intune/configuration/custom-settings-configure)



### <a name="device-type-restrictions"></a>장치 유형 제한

Microsoft Managed Desktop Intune에 등록할 수 있어야 합니다.

**준비되지 않음**

현재 하나 이상의 등록 제한 정책이 구성되어 있는 경우 Windows Intune에 등록할 수 없습니다. Microsoft Managed Desktop 사용자를 [](/mem/intune/enrollment/enrollment-restrictions-set) 대상으로 하는 각 등록 제한 정책에 대한 등록 제한 설정의 단계를 따르고 **MDM(Windows)** 설정을 허용으로 **변경합니다.** 그러나 MDM(개인  소유의 모든 **MDM) Windows** 차단으로 설정할 **수 있습니다.** 


### <a name="enrollment-status-page"></a>등록 상태 페이지

현재 ESP(등록 상태 페이지)를 사용하도록 설정되어 있습니다. 이 기능의 공개 미리 Microsoft Managed Desktop 참여하려는 경우 이 항목을 무시해도 됩니다. 자세한 내용은 [Autopilot의](../get-started/esp-first-run.md)첫 실행 환경 및 등록 상태 페이지를 참조하세요.

**준비되지 않음**

ESP 기본 프로필이 앱 및 프로필 구성 진행률 표시로 **설정되어 있습니다.** 이 설정을 사용하지 않도록 설정하거나 Set [up the Enrollment Status Page의](/mem/intune/enrollment/windows-enrollment-status)단계를 수행하여 Azure AD Microsoft Managed Desktop 장치에 대한 할당이 포함되어 있지 않은지 확인하십시오.

**권고**

앱 및 프로필 구성 진행률 표시 설정이 있는 프로필이 Microsoft Managed Desktop 포함된 Azure AD 그룹에 할당되지 Microsoft Managed Desktop 합니다.  자세한 내용은 [Set up the Enrollment Status Page을 참조하십시오.](/mem/intune/enrollment/windows-enrollment-status)

### <a name="microsoft-store-for-business"></a>비즈니스용 Microsoft Store

비즈니스용 Microsoft Store 및 회사 포털 앱을 배포하여 Microsoft Managed Desktop 앱과 Microsoft Microsoft Project(허용되는 경우)과 같은 일부 Visio 설치할 수 있습니다.

**준비되지 않음**

비즈니스용 Microsoft Store 활성화되지 않은 경우 또는 Intune과 동기화되지 않습니다. 자세한 내용은 장치에서 [](/mem/intune/apps/windows-store-for-business) 대량 구매 앱을 관리하는 방법 및 비즈니스용 Microsoft Store 디바이스에 Microsoft Intune [앱을 Intune 회사 포털 참조하세요.](../get-started/company-portal.md)

### <a name="multifactor-authentication"></a>다단계 인증

다단계 인증을 통해 Microsoft Managed Desktop Azure AD에서 Azure AD 조직(테넌트)을 관리할 수 없습니다.


**준비되지 않음**

모든 사용자에게 할당된 조건부 액세스  정책에 필요한 일부 다단계 인증 정책이 설정되어 있습니다. 등록하는 동안 관련 조건부 액세스 Microsoft Managed Desktop 서비스 계정을 제외하고 이러한 계정에 대한 액세스를 제한하기 위해 새 조건부 액세스 정책을 적용합니다. 이러한 서비스 계정에 대한 자세한 내용은 표준 운영 [절차 를 참조합니다.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**권고**

조건부 액세스 정책에 다단계 인증이 필요하여 Microsoft Managed Desktop 서비스를 관리할 Microsoft Managed Desktop 있습니다. 등록하는 동안 관련 조건부 액세스 Microsoft Managed Desktop 서비스 계정을 제외하고 이러한 계정에 대한 액세스를 제한하기 위해 새 조건부 액세스 정책을 적용합니다. 이러한 서비스 계정에 대한 자세한 내용은 표준 운영 [절차 를 참조합니다.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**오류**

Intune 관리자 역할에는 이 검사에 대한 충분한 권한이 없습니다. 이 검사를 실행하려면 다음 Azure AD 역할도 할당해야 합니다.

- 보안 읽기 권한자
- 보안 관리자
- 조건부 액세스 관리자
- 전역 읽기 권한자
- 장치 관리자


### <a name="powershell-scripts"></a>PowerShell 스크립트

Windows PowerShell 디바이스를 대상으로 하는 방식으로 스크립트를 할당할 Microsoft Managed Desktop 없습니다.  

**권고**

Azure AD Windows PowerShell 스크립트가 Microsoft Manage Desktop 장치 또는 사용자를 대상으로 하지 않는지 확인 모든 사용자, 모든 장치 또는 둘 다를 대상으로 하는 PowerShell 스크립트를 할당하지 않습니다. 모든 장치 또는 사용자를 포함하지 않는 특정 Azure AD 그룹을 대상으로 하는 할당을 Microsoft Managed Desktop 변경합니다. 자세한 내용은 [Intune에서 Windows 10 PowerShell 스크립트 사용을 참조하세요.](/mem/intune/apps/intune-management-extension)

### <a name="region"></a>지역

지역은 해당 지역의 지원이 Microsoft Managed Desktop.

**준비되지 않음**

Azure AD 조직 지역은 현재 조직에서 지원되지 Microsoft Managed Desktop. 자세한 내용은 [지원되는 Microsoft Managed Desktop 및 언어를 참조하세요.](../service-description/regions-languages.md)

**권고**

Azure AD 조직이 있는 국가 중 하나 이상이 조직에서 지원되지 Microsoft Managed Desktop. 자세한 내용은 [지원되는 Microsoft Managed Desktop 및 언어를 참조하세요.](../service-description/regions-languages.md)


### <a name="security-baselines"></a>보안 기준

보안 기준 정책은 모든 디바이스를 대상으로 Microsoft Managed Desktop 않습니다.

**준비되지 않음**

모든 사용자, 모든 장치 또는 둘 다를 대상으로 하는 보안 기준 프로필이 있습니다. 모든 디바이스를 포함하지 않는 특정 Azure AD 그룹을 대상으로 하는 할당을 Microsoft Managed Desktop 변경합니다. 단계에 대한 자세한 내용은 [Use security baselines to configure Windows 10 devices in Intune을 참조하세요.](/mem/intune/protect/security-baselines) 등록하는 동안 모든 디바이스에 새 보안 기준을 Microsoft Managed Desktop 있습니다. 등록 후 Microsoft Managed Desktop 정책 영역의 보안 기준 정책을 검토할 수 Microsoft Endpoint Manager. 

**권고**

디바이스에서 제외한 보안 기준 정책이 Microsoft Managed Desktop 합니다. 단계에 대한 자세한 내용은 [Use security baselines to configure Windows 10 devices in Intune을 참조하세요.](/mem/intune/protect/security-baselines) 등록하는 동안 모든 디바이스에 새 보안 기준을 Microsoft Managed Desktop 있습니다. 최신 작업 공간 **장치 - 모든** Azure AD 그룹은 등록할 때 만드는 동적 그룹이기 때문에 Microsoft Managed Desktop 등록 후 이 그룹을 제외하기 위해 돌아와야 합니다. 

### <a name="unlicensed-admins"></a>라이선스가 없는 관리자

Azure AD 조직과 상호 작용할 때 "사용 권한 부족" 오류를 방지하려면 이 설정을 사용하도록 설정해야 합니다. 

**준비되지 않음**

**라이선스가** 없는 관리자에 대한 액세스 허용을 사용하도록 설정해야 합니다. 단계에 대한 자세한 내용은 게스트 계정에 대한 [사전 준비를 참조하세요.](/microsoft-365/managed-desktop/get-ready/guest-accounts)

### <a name="windows-apps"></a>Windows 앱

사용자가 사용할 Microsoft Managed Desktop 앱을 검토합니다.

**권고**

사용자가 보유할 앱의 인벤토리를 Microsoft Managed Desktop 합니다. 이러한 앱은 Intune에서 배포해야 하기 때문에 기존 Intune 앱을 다시 사용하는지 평가합니다. 앱을 회사 포털(장치에 Intune 회사 포털 [](../get-started/company-portal.md) 설치 및 ESP(등록 상태 페이지)를 참조하여 사용자에게 앱을 배포하는 것이 좋습니다. 자세한 내용은 [Autopilot의](../get-started/esp-first-run.md)Microsoft Managed Desktop 및 첫 실행 환경의 앱 및 등록 상태 페이지를 참조하세요. [](apps.md)

Microsoft 계정 담당자에게 Intune으로 마이그레이션할 준비가 되거나 Microsoft Endpoint Configuration Manager 앱을 식별할 수 있는 쿼리를 요청할 수 있습니다.


### <a name="windows-hello-for-business"></a>비즈니스용 Windows Hello

Microsoft Managed Desktop 비즈니스용 Windows Hello 사용하도록 설정해야 합니다.

**권고**

Windows Hello 비즈니스용 전자 메일이 사용하지 않도록 설정되거나 설정되지 않았습니다. Create a Windows Hello [for Business policy의 단계를 수행하여 사용하도록 설정하세요.](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)


### <a name="windows-10-update-rings"></a>Windows 10 업데이트 링

Intune의 "Windows 10 업데이트 링" 정책은 모든 Microsoft Managed Desktop 없습니다.

**준비되지 않음**

모든 장치, 모든 사용자 또는 둘 다를 대상으로 하는 "업데이트 링" 정책이 있습니다. 모든 디바이스를 포함하지 않는 특정 Azure AD 그룹을 대상으로 하는 Assignment를 Microsoft Managed Desktop 변경합니다. 단계는 [Intune에서 Windows 10 업데이트 관리를 참조하세요.](/mem/intune/protect/windows-update-for-business-configure)

**권고**

최신 작업 공간 장치 **-All** Azure AD 그룹을 제외한 모든 업데이트 링 정책이 있는지 확인 합니다. 이러한 정책에 Azure AD 사용자 그룹을 할당한 경우, 사용자 또는 동등한 그룹에 사용자를 추가하는 최신 **Workplace -All** Azure AD 그룹도 Microsoft Managed Desktop 있는지 확인 합니다. 단계는 [Intune에서 Windows 10 업데이트 관리를 참조하세요.](/mem/intune/protect/windows-update-for-business-configure) 최신 작업 공간 장치 **-All** 및 **Modern Workplace -모든** Azure AD 그룹은 사용자가 Microsoft Managed Desktop 때 만드는 그룹이기 때문에 등록 후 이 그룹을 제외하기 위해 다시 돌아와야 합니다.


## <a name="azure-active-directory-settings"></a>Azure Active Directory 설정

Azure Portal에서 Azure Active Directory [설정에 액세스할 수 있습니다.](https://portal.azure.com)

### <a name="intune-enrollment"></a>Intune 등록

Windows 10 Azure AD 조직의 디바이스에서 Intune에 자동으로 등록할 수 있어야 합니다.

**권고**

**MDM 사용자** 범위가 없음이 아닌 **일부** 또는 **모두로** 설정되어 있는지 **확인** 일부 **를** 선택한 경우 등록 후 돌아와서 모든 사용자  그룹을 대상으로 하는 그룹 또는 동등한 그룹에 대한 최신 작업 공간 **-all** Azure AD Microsoft Managed Desktop 선택합니다.  자세한 [내용은 Set up enrollment for Windows by using Microsoft Intune.](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

### <a name="ad-hoc-subscriptions"></a>애드 호 구독

"false"로 설정하면 상태 로밍이 제대로 Enterprise 수 있는 설정을 검사하는 방법에 대해 조언합니다.

**권고**

**AllowAdHocSubscriptions가** True로 설정되어 **있는지 확인** 그렇지 않으면 Enterprise 로밍이 작동하지 않을 수 있습니다. 자세한 내용은 [Set-MsolCompanySettings를 참조하세요.](/powershell/module/msonline/set-msolcompanysettings)


### <a name="enterprise-state-roaming"></a>Enterprise State Roaming

Enterprise 상태 로밍을 사용하도록 설정해야 합니다.

**권고**

선택한 그룹에 Enterprise 상태 로밍이 사용하도록  **설정되어 있는지** 확인합니다. 자세한 내용은 에서 Enterprise 상태 로밍 사용 [을 Azure Active Directory.](/azure/active-directory/devices/enterprise-state-roaming-enable)

### <a name="licenses"></a>라이선스

라이선스를 사용하려면 여러 라이선스가 Microsoft Managed Desktop.

**준비되지 않습니다.**

사용자에 대해 사용하는 데 필요한 모든 라이선스가 Microsoft Managed Desktop. 자세한 내용은 Microsoft Managed Desktop [기술](../intro/technologies.md) 및 [라이선스에 대한 자세한 정보를 참조하세요.](prerequisites.md#more-about-licenses)


### <a name="microsoft-managed-desktop-service-accounts"></a>Microsoft Managed Desktop 서비스 계정

특정 계정 이름은 Microsoft Managed Desktop 서비스를 관리하기 위해 만든 계정 이름과 Microsoft Managed Desktop 있습니다.

**준비되지 않음**

계정 이름이 하나 이상 있는 경우 계정 이름이 계정 이름으로 Microsoft Managed Desktop. Microsoft 계정 담당자와 함께 이러한 계정 이름을 제외합니다. 보안 위험을 최소화하기 위해 계정 이름을 공개적으로 나열하지 않습니다. 


### <a name="security-administrator-roles"></a>보안 관리자 역할

특정 보안 역할이 있는 사용자는 끝점용 Microsoft Defender에서 해당 역할을 할당해야 합니다.

**권고**

Azure AD 조직에서 이러한 역할에 할당된 사용자가 있는 경우 이러한 역할도 끝점용 Microsoft Defender에서 할당해야 합니다. 그렇지 않으면 이러한 역할이 있는 관리자는 관리 포털에 액세스할 수 없습니다.

- 보안 운영자
- 전역 읽기 권한자

자세한 내용은 역할 기반 액세스 제어에 대한 역할 만들기 [및 관리를 참조하세요.](/windows/security/threat-protection/microsoft-defender-atp/user-roles)


### <a name="security-default"></a>보안 기본값

보안 기본값은 Azure Active Directory 장치를 관리하지 Microsoft Managed Desktop 방지합니다.

**준비되지 않음**

보안 기본값이 설정되어 있습니다. 보안 기본값을 해제하고 조건부 액세스 정책을 설정합니다. 자세한 내용은 [일반적인 조건부 액세스 정책 을 참조하세요.](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)

### <a name="self-service-password-reset"></a>셀프 서비스 암호 재설정

SSPR(셀프 서비스 암호 재설정)은 서비스 계정을 제외한 Microsoft Managed Desktop 모든 사용자에 대해 Microsoft Managed Desktop 수 있습니다. 자세한 내용은 자습서: 셀프 서비스 암호 재설정을 사용하여 사용자의 계정 잠금을 해제하거나 암호를 [Azure Active Directory 수 있습니다.를 참조하세요.](/azure/active-directory/authentication/tutorial-enable-sspr)

**권고**

**SSPR** 선택 설정에 사용자가 포함되지만 Microsoft Managed Desktop 계정은 Microsoft Managed Desktop 합니다. Microsoft Managed Desktop SSPR을 사용하도록 설정하면 서비스 계정이 예상대로 작동하지 않습니다.  


### <a name="standard-user-role"></a>표준 사용자 역할

전역 관리자 및 장치 관리자의 Azure AD 역할이 할당된 사용자 Microsoft Managed Desktop 사용자만 로컬 관리자 권한이 없는 표준 사용자입니다. 다른 모든 사용자에게는 디바이스를 시작할 때 표준 사용자 Microsoft Managed Desktop 할당됩니다.

**권고**

Microsoft Managed Desktop 등록한 후 사용자의 Microsoft Managed Desktop 로컬 관리자 권한이 없습니다.

## <a name="microsoft-365-apps-for-enterprise"></a>엔터프라이즈용 Microsoft 365 앱

### <a name="onedrive"></a>OneDrive

특정 **도메인에** 가입된 PC에서만 동기화 허용 설정은 Microsoft Managed Desktop. OneDrive 관리 센터에서 OneDrive [수 있습니다.](https://admin.onedrive.com)

**권고**

특정 도메인에 가입된 PC에서만 동기화 허용 **설정을 사용하고** 있습니다. 이 설정은 사용자에 대해 작동하지 Microsoft Managed Desktop. 이 설정을 사용하지 않도록 설정하고 대신 조건부 OneDrive 정책을 사용할 수 있도록 설정을 합니다. 자세한 [내용은 Plan a Conditional Access deployment을](/azure/active-directory/conditional-access/plan-conditional-access) 참조합니다.
