---
title: 준비 평가 도구에서 발견한 문제 해결
description: 도구에서 찾은 각 문제에서 수행할 자세한 작업
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 360cd50556b77f141d1585f42ac08ee5990b4851
ms.sourcegitcommit: f3059a0065496623e36e5a084cd2291e6b844597
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2021
ms.locfileid: "50040523"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>준비 평가 도구에서 발견한 문제 해결

각 검사에 대해 도구는 다음 네 가지 결과 중 하나를 보고합니다.


|결과  |의미  |
|---------|---------|
|준비     | 등록을 완료하기 전에 필요한 작업은 없습니다.        |
|권고    | 등록과 사용자에 대한 최상의 환경을 위해 도구 또는 이 문서의 단계를 따르세요. *등록을* 완료할 수 있지만 첫 번째 장치를 배포하기 전에 이러한 문제를 해결해야 합니다.        |
|준비되지 않음 | *이러한 문제를 해결하지 않는 경우 등록이 실패합니다.* 도구 또는 이 문서의 단계에 따라 문제를 해결합니다.        |
|오류 | 사용중인 Azure AD(Active Directory) 역할에 이 검사를 실행할 수 있는 권한이 없습니다. |

> [!NOTE]
> 이 도구에서 보고한 결과에는 설정이 실행된 특정 시점에만 설정 상태가 반영됩니다. 나중에 Microsoft Intune, Azure Active Directory 또는 Microsoft 365에서 정책을 변경하면 "준비되지 않은" 항목이 될 수 있습니다. Microsoft Managed Desktop 작업의 문제를 방지하려면 정책을 변경하기 전에 이 문서에 설명된 특정 설정을 확인합니다.

## <a name="microsoft-intune-settings"></a>Microsoft Intune 설정

Microsoft Endpoint Manager 관리 센터에서 Intune 설정에 [액세스할 수 있습니다.](https://endpoint.microsoft.com)

### <a name="autopilot-deployment-profile"></a>Autopilot 배포 프로필

Microsoft Managed Desktop 장치를 사용하여 할당되거나 동적 그룹을 대상으로 하는 기존 Autopilot 프로필은 없습니다. Microsoft Managed Desktop은 Autopilot을 사용하여 새 장치를 프로비전합니다.

**준비되지 않음**

모든 장치에 할당된 Autopilot 프로필이 있습니다. 단계는 Windows [Autopilot을 사용하여 Intune에서 Windows 장치 등록을 참조하세요.](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot) Microsoft Managed Desktop 등록 후 Autopilot 정책을 설정하여 최신 **Workplace Devices -All** Azure AD 그룹을 제외합니다.

**권고**

Autopilot 프로필이 Microsoft Managed Desktop 장치를 포함하지 않는 할당되거나 동적 Azure AD 그룹을 대상으로 하는지 확인 단계는 Windows [Autopilot을 사용하여 Intune에서 Windows 장치 등록을 참조하세요.](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot) Microsoft Managed Desktop 등록 후 Autopilot 프로필을 설정하여 최신 작업 공간 장치 **- 모든** Azure AD 그룹을 제외합니다.


### <a name="certificate-connectors"></a>인증서 커넥터

Microsoft Managed Desktop에 등록하려는 장치에서 사용할 인증서 커넥터가 있는 경우 커넥터에 오류가 없습니다. 다음 권고 중 하나만 상황에 적용될 것이기 때문에 신중하게 검토하십시오.

**권고**

인증서 커넥터가 없습니다. 커넥터가 필요하지 않을 수도 있지만 Microsoft Managed Desktop 장치에서 네트워크 연결을 위해 일부 커넥터가 필요한지 평가해야 합니다. 자세한 내용은 Microsoft Managed Desktop에 대한 인증서 및 네트워크 프로필 [준비를 참조하세요.](certs-wifi-lan.md)

**권고**

하나 이상의 인증서 커넥터에 오류가 있습니다. Microsoft Managed Desktop 장치에 인증서를 제공하기 위해 이 커넥터가 필요한 경우 오류를 해결해야 합니다. 자세한 내용은 Microsoft Managed Desktop에 대한 인증서 및 네트워크 프로필 [준비를 참조하세요.](certs-wifi-lan.md)


**권고**

인증서 커넥터가 하나 이상 있으며 오류가 보고되지 않습니다. 그러나 배포를 준비할 때 Microsoft Managed Desktop 디바이스용 커넥터를 다시 사용할 프로필을 만들어야 할 수 있습니다. 자세한 내용은 Microsoft Managed Desktop에 대한 인증서 및 네트워크 프로필 [준비를 참조하세요.](certs-wifi-lan.md)


### <a name="conditional-access-policies"></a>조건부 액세스 정책

조건부 액세스 정책은 Microsoft Managed Desktop이 Intune 및 Azure AD에서 Azure AD 조직(테넌트)을 관리하는 것을 방지하지 말아야 합니다.

**준비되지 않음**

모든 사용자를 대상으로 하는 조건부 액세스 정책이 하나 이상 있습니다. 등록하는 동안 Microsoft Managed Desktop 서비스 계정을 관련 조건부 액세스 정책에서 제외하고 이러한 계정에 대한 액세스를 제한하기 위해 새 조건부 액세스 정책을 적용합니다. 등록 후 Microsoft Endpoint Manager에서 Microsoft Managed Desktop 조건부 액세스 정책을 검토할 수 있습니다. 이러한 서비스 계정에 대한 자세한 내용은 Standard 운영 절차를 [참조합니다.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**권고**

Microsoft Managed Desktop이 Microsoft Managed Desktop 서비스를 관리하지 못하게 할 수 있는 조건부 액세스 정책이 있습니다. 등록하는 동안 Microsoft Managed Desktop 서비스 계정을 관련 조건부 액세스 정책에서 제외하고 이러한 계정에 대한 액세스를 제한하기 위해 새 조건부 액세스 정책을 적용합니다. 이러한 서비스 계정에 대한 자세한 내용은 Standard 운영 절차를 [참조합니다.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**오류**

Intune 관리자 역할에 이 검사에 대한 충분한 권한이 없습니다. 이 검사를 실행하려면 다음 Azure AD 역할도 할당해야 합니다.

- 보안 읽기 권한자
- 보안 관리자
- 조건부 액세스 관리자
- 전역 읽기 권한자
- 장치 관리자


### <a name="device-compliance-policies"></a>장치 준수 정책

Azure AD 조직의 Intune 장치 준수 정책은 Microsoft Managed Desktop 장치에 영향을 줄 수 있습니다.

**준비되지 않음**

모든 사용자를 대상으로 하는 규정 준수 정책이 하나 이상 있습니다. Microsoft Managed Desktop에는 Microsoft Managed Desktop 장치를 대상으로 하는 준수 정책이 포함되어 있습니다.  Microsoft Managed Desktop 사용자 또는 장치를 포함하지 않는 특정 Azure AD 그룹을 대상으로 하는 정책을 변경합니다. 자세한 단계는 [Microsoft Intune에서 준수 정책 만들기를 참조하세요.](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)

**권고**

Microsoft Managed Desktop 사용자를 대상으로 지정하지 않은 준수 정책이 있는지 확인 자세한 단계는 [Microsoft Intune에서 준수 정책 만들기를 참조하세요.](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)



### <a name="device-configuration-profiles"></a>장치 구성 프로필

Azure AD 조직의 Intune 장치 구성 프로필은 Microsoft Manage Desktop 장치 또는 사용자를 대상으로 지정하지 말아야 합니다.

**준비되지 않음**

모든 사용자, 모든 장치 또는 둘 다를 대상으로 하는 구성 프로필이 하나 이상 있습니다. 프로필을 다시 설정하여 Microsoft Managed Desktop 장치를 포함하지 않는 특정 Azure AD 그룹을 대상으로 지정합니다. 단계는 Microsoft [Intune에서](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)사용자 지정 설정을 사용하여 프로필 만들기를 참조하세요.

**권고**

Microsoft Managed Desktop 장치 또는 사용자를 포함하지 않은 구성 정책이 있는지 확인 단계는 Microsoft [Intune에서](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)사용자 지정 설정을 사용하여 프로필 만들기를 참조하세요.



### <a name="device-type-restrictions"></a>장치 유형 제한

Microsoft Managed Desktop 장치는 Intune에 등록할 수 있어야 합니다.

**준비되지 않음**

현재 Windows 장치가 Intune에 등록되지 않도록 등록 제한 정책을 하나 이상 구성했습니다. Microsoft Managed [](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) Desktop 사용자를 대상으로 하는 각 등록 제한 정책에 대한 등록 제한 설정의 단계를 따르고 **Windows(MDM)** 설정을 허용으로 **변경합니다.** 그러나 개인  **소유의 Windows(MDM)** 장치를 차단으로 설정할 수 **있습니다.** 


### <a name="enrollment-status-page"></a>등록 상태 페이지

현재 ESP(등록 상태 페이지)를 사용하도록 설정되어 있습니다. 이 기능의 Microsoft Managed Desktop 공개 미리 보기에 참여하려는 경우 이 항목을 무시해도 됩니다. 자세한 내용은 Autopilot 및 등록 상태 페이지의 첫 실행 [환경을 참조하세요.](../get-started/esp-first-run.md)

**준비되지 않음**

ESP 기본 프로필이 앱 및 프로필 구성 진행률 표시로 **설정되어 있습니다.** 등록 상태 설정 페이지의 단계에 따라 이 설정을 사용하지 않도록 설정하거나 Azure AD 그룹에 대한 할당에 Microsoft Managed Desktop 장치가 포함되어 [있지 않은지 확인하십시오.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)

**권고**

앱 및 프로필 구성 진행률 표시 설정이 있는 프로필이 Microsoft Managed Desktop 장치를 포함하는 Azure AD 그룹에 할당되지 않은지 확인  자세한 내용은 등록 상태 페이지 [설정을 참조하십시오.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)

### <a name="microsoft-store-for-business"></a>비즈니스용 Microsoft Store

Microsoft는 비즈니스용 Microsoft Store를 사용하며 Microsoft Managed Desktop에 회사 포털 앱을 배포하여 사용자가 Microsoft Project 및 Microsoft Visio(허용되는 경우)과 같은 일부 앱을 선택적으로 설치할 수 있도록 합니다.

**준비되지 않음**

비즈니스용 Microsoft Store를 사용하도록 설정하지 않은 경우 또는 Intune과 동기화되지 않습니다. 자세한 내용은 장치에서 [Microsoft Intune 및 Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) 회사 포털을 설치하여 비즈니스용 Microsoft Store에서 대량 구매 앱을 관리하는 [방법을 참조하세요.](../get-started/company-portal.md)

### <a name="multifactor-authentication"></a>다단계 인증

다단계 인증을 통해 Microsoft Managed Desktop이 Intune 및 Azure AD에서 Azure AD 조직(테넌트)을 관리할 수 없습니다.


**준비되지 않음**

모든 사용자에게 할당된 조건부 액세스  정책에 필요한 몇 가지 다단계 인증 정책이 설정되어 있습니다. 등록하는 동안 Microsoft Managed Desktop 서비스 계정을 관련 조건부 액세스 정책에서 제외하고 이러한 계정에 대한 액세스를 제한하기 위해 새 조건부 액세스 정책을 적용합니다. 이러한 서비스 계정에 대한 자세한 내용은 Standard 운영 절차를 [참조합니다.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**권고**

Microsoft Managed Desktop이 Microsoft Managed Desktop 서비스를 관리하지 못하도록 하는 조건부 액세스 정책에 다단계 인증이 필요합니다. 등록하는 동안 Microsoft Managed Desktop 서비스 계정을 관련 조건부 액세스 정책에서 제외하고 이러한 계정에 대한 액세스를 제한하기 위해 새 조건부 액세스 정책을 적용합니다. 이러한 서비스 계정에 대한 자세한 내용은 Standard 운영 절차를 [참조합니다.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**오류**

Intune 관리자 역할에 이 검사에 대한 충분한 권한이 없습니다. 이 검사를 실행하려면 다음 Azure AD 역할도 할당해야 합니다.

- 보안 읽기 권한자
- 보안 관리자
- 조건부 액세스 관리자
- 전역 읽기 권한자
- 장치 관리자


### <a name="powershell-scripts"></a>PowerShell 스크립트

Windows PowerShell Microsoft Managed Desktop 장치를 대상으로 하는 방식으로 스크립트를 할당할 수 없습니다.  

**권고**

Azure AD Windows PowerShell 스크립트가 Microsoft Manage Desktop 장치 또는 사용자를 대상으로 하지 않는지 확인 모든 사용자, 모든 장치 또는 둘 다를 대상으로 하는 PowerShell 스크립트를 할당하지 않습니다. Microsoft Managed Desktop 장치 또는 사용자를 포함하지 않는 특정 Azure AD 그룹을 대상으로 하는 할당을 사용하도록 정책을 변경합니다. 자세한 내용은 [Intune의 Windows 10 장치에서 PowerShell 스크립트 사용을 참조하세요.](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)

### <a name="region"></a>Region

해당 지역은 Microsoft Managed Desktop에서 지원해야 합니다.

**준비되지 않음**

Azure AD 조직 지역은 현재 Microsoft Managed Desktop에서 지원되지 않습니다. 자세한 내용은 Microsoft Managed Desktop 지원 지역 및 [언어를 참조하세요.](../service-description/regions-languages.md)

**권고**

Azure AD 조직이 있는 하나 이상의 국가는 Microsoft Managed Desktop에서 지원되지 않습니다. 자세한 내용은 Microsoft Managed Desktop 지원 지역 및 [언어를 참조하세요.](../service-description/regions-languages.md)


### <a name="security-baselines"></a>보안 기준

보안 기준 정책은 Microsoft Managed Desktop 장치를 대상으로 하지 말아야 합니다.

**준비되지 않음**

모든 사용자, 모든 장치 또는 둘 다를 대상으로 하는 보안 기준 프로필이 있습니다. Microsoft Managed Desktop 장치를 포함하지 않는 특정 Azure AD 그룹을 대상으로 하는 할당을 사용하도록 정책을 변경합니다. 단계는 보안 기준을 사용하여 [Intune에서 Windows 10 디바이스를 구성하는 방법을 참조하세요.](https://docs.microsoft.com/mem/intune/protect/security-baselines)

**권고**

Microsoft Managed Desktop 장치를 제외한 보안 기준 정책이 있는지 확인 단계는 보안 기준을 사용하여 [Intune에서 Windows 10 디바이스를 구성하는 방법을 참조하세요.](https://docs.microsoft.com/mem/intune/protect/security-baselines) 최신 **Workplace Devices -All** Azure AD 그룹은 Microsoft Managed Desktop에 등록할 때 만드는 동적 그룹이기 때문에 등록 후 이 그룹을 제외하기 위해 돌아와야 합니다.


### <a name="windows-apps"></a>Windows 앱

Microsoft Managed Desktop 사용자에게 필요한 앱을 검토합니다.

**권고**

Microsoft Managed Desktop 사용자에게 필요한 앱의 인벤토리를 준비해야 합니다. 이러한 앱은 Intune에서 배포해야 하기 때문에 기존 Intune 앱을 다시 사용하는지 평가합니다. 회사 포털(장치에 [Intune 회사](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) 포털 설치 및 ESP(등록 상태 페이지) 참조)을 사용하여 사용자에게 앱을 배포하는 것이 좋습니다. 자세한 내용은 Autopilot 및 등록 상태 페이지에서 [Microsoft Managed Desktop의](apps.md) 앱 및 첫 실행 환경을 [참조하세요.](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run)

Microsoft Endpoint Configuration Manager의 쿼리를 Microsoft 계정 담당자에게 요청하여 Intune으로 마이그레이션할 준비가 되거나 조정이 필요한 앱을 식별할 수 있습니다.


### <a name="windows-hello-for-business"></a>비즈니스용 Windows Hello

Microsoft Managed Desktop을 사용하려면 비즈니스용 Windows Hello를 사용하도록 설정해야 합니다.

**준비되지 않음**

비즈니스용 Windows Hello를 사용할 수 없습니다. 비즈니스용 [Windows Hello](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy) 만들기 정책의 단계에 따라 사용하도록 설정

**권고**

비즈니스용 Windows Hello가 설정되지 않습니다. 비즈니스용 Windows Hello 만들기 정책의 단계에 따라 사용하도록 [설정하십시오.](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)


### <a name="windows-10-update-rings"></a>Windows 10 업데이트 링

Intune의 "Windows 10 업데이트 링" 정책은 Microsoft Managed Desktop 장치를 대상으로 지정하지 말아야 합니다.

**준비되지 않음**

모든 장치, 모든 사용자 또는 둘 다를 대상으로 하는 "업데이트 링" 정책이 있습니다. Microsoft Managed Desktop 장치를 포함하지 않는 특정 Azure AD 그룹을 대상으로 하는 할당을 사용하도록 정책을 변경합니다. 단계는 [Intune에서 Windows 10 소프트웨어 업데이트 관리를 참조하세요.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)

**권고**

최신 작업 공간 장치 -All Azure AD 그룹을 제외한 모든 업데이트 **링** 정책이 있는지 확인 합니다. 이러한 정책에 Azure AD 사용자 그룹을 할당한 경우 Microsoft Managed Desktop 사용자를 추가하는 최신 **Workplace -All** Azure AD 그룹(또는 동등한 그룹)도 제외한 업데이트 링 정책이 있는지 확인하세요. 단계는 [Intune에서 Windows 10 소프트웨어 업데이트 관리를 참조하세요.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure) 최신 작업 공간 장치 **-All** 및 **Modern Workplace -All** Azure AD 그룹은 Microsoft Managed Desktop에 등록할 때 만든 그룹이기 때문에 등록 후 이 그룹을 제외하기 위해 다시 돌아와야 합니다.


## <a name="azure-active-directory-settings"></a>Azure Active Directory 설정

Azure Portal에서 Azure Active Directory [설정에 액세스할 수 있습니다.](https://portal.azure.com)

### <a name="intune-enrollment"></a>Intune 등록

Azure AD 조직의 Windows 10 장치는 Intune에 자동으로 등록할 수 있어야 합니다.

**권고**

**MDM 사용자** 범위가 **없음이** 아닌 일부 또는 모두로 설정되어 있는지 **확인** 일부를 선택하는 경우 등록 후 다시 돌아와서 모든 Microsoft Managed Desktop 사용자를 대상으로 하는 그룹용 최신 **Workplace -All** Azure AD **그룹** 또는 동등한 그룹을 선택합니다.  Microsoft Intune을 사용하여 Windows 장치에 대한 등록 [설정을 참조합니다.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)


### <a name="ad-hoc-subscriptions"></a>Ad Hoc 구독

"false"로 설정하면 엔터프라이즈 상태 로밍이 제대로 작동하지 않을 수 있는 설정을 검사하는 방법을 알 수 있습니다.

**권고**

**AllowAdHocSubscriptions가** **True로** 설정되어 있도록 합니다. 그렇지 않으면 엔터프라이즈 상태 로밍이 작동하지 않을 수 있습니다. 자세한 내용은 [Set-MsolCompanySettings를 참조하십시오.](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)


### <a name="enterprise-state-roaming"></a>Enterprise State Roaming

엔터프라이즈 상태 로밍을 사용하도록 설정해야 합니다.

**권고**

Enterprise State Roaming이 전체  또는 선택한 그룹에 대해 사용하도록 **설정되어 있는지** 확인합니다. 자세한 내용은 Azure Active Directory에서 엔터프라이즈 상태 [로밍 사용을 참조하세요.](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)

### <a name="licenses"></a>라이선스

Microsoft Managed Desktop을 사용하려면 여러 라이선스가 필요합니다.

**준비되지 않은 경우**

Microsoft Managed Desktop을 사용하는 데 필요한 모든 라이선스가 없습니다. 자세한 내용은 [Microsoft Managed Desktop 기술](../intro/technologies.md) 및 [라이선스에 대한 자세한 정보를 참조하세요.](prerequisites.md#more-about-licenses)


### <a name="security-account-names"></a>보안 계정 이름

특정 보안 계정 이름이 Microsoft Managed Desktop에서 만든 이름과 충돌할 수 있습니다.

**준비되지 않음**

하나 이상의 계정 이름이 Microsoft Managed Desktop에서 만든 계정 이름과 충돌합니다. Microsoft 계정 담당자와 함께 이러한 계정 이름을 제외합니다.


### <a name="security-administrator-roles"></a>보안 관리자 역할

특정 보안 역할이 있는 사용자는 끝점용 Microsoft Defender에서 해당 역할을 할당해야 합니다.

**권고**

Azure AD 조직에서 이러한 역할에 할당된 사용자가 있는 경우 이러한 역할도 끝점용 Microsoft Defender에 할당해야 합니다. 그렇지 않으면 이러한 역할이 있는 관리자가 관리 포털에 액세스할 수 없습니다.

- 보안 운영자
- 전역 읽기 권한자

자세한 내용은 역할 기반 액세스 제어에 대한 역할 만들기 [및 관리를 참조하세요.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)


### <a name="security-default"></a>보안 기본값

Azure Active Directory의 보안 기본값은 Microsoft Managed Desktop이 디바이스를 관리하지 못하게 합니다.

**준비되지 않음**

보안 기본값이 설정되어 있습니다. 보안 기본값을 해제하고 조건부 액세스 정책을 설정합니다. 자세한 내용은 [일반적인 조건부 액세스 정책을 참조하십시오.](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)

### <a name="self-service-password-reset"></a>셀프 서비스 암호 재설정

Microsoft Managed Desktop 서비스 계정을 제외한 모든 Microsoft Managed Desktop 사용자에 대해 SSPR(셀프 서비스 암호 재설정)을 사용하도록 설정할 수 있습니다. 자세한 내용은 [자습서: 사용자가 Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)셀프 서비스 암호 재설정을 사용하여 계정 잠금을 해제하거나 암호를 재설정할 수 있도록 합니다.

**권고**

**SSPR** 선택 설정에 Microsoft Managed Desktop 사용자가 포함되지만 Microsoft Managed Desktop 서비스 계정은 제외해야 합니다. SSPR을 사용하도록 설정하면 Microsoft Managed Desktop 서비스 계정이 예상대로 작동하지 않습니다.  


### <a name="standard-user-role"></a>표준 사용자 역할

전역 관리자 및 장치 관리자의 Azure AD 역할이 할당된 사용자 이외에 Microsoft Managed Desktop 사용자는 로컬 관리자 권한이 없는 표준 사용자입니다. 다른 모든 사용자에게는 Microsoft Managed Desktop 장치를 시작할 때 표준 사용자 역할이 할당됩니다.

**권고**

Microsoft Managed Desktop 사용자에게는 등록 후 Microsoft Managed Desktop 디바이스에 대한 로컬 관리자 권한이 없습니다.

## <a name="microsoft-365-apps-for-enterprise"></a>엔터프라이즈용 Microsoft 365 앱

### <a name="onedrive"></a>OneDrive

특정 **도메인에 가입된 PC에서만** 동기화 허용 설정이 Microsoft Managed Desktop과 충돌합니다. OneDrive 관리 센터에서 OneDrive 설정에 [액세스할 수 있습니다.](https://admin.onedrive.com)

**권고**

특정 도메인 설정에 가입된 PC에서만 동기화 **허용을 사용 중입니다.** 이 설정은 Microsoft Managed Desktop에서는 작동하지 않습니다. 이 설정을 사용하지 않도록 설정하고 대신 조건부 액세스 정책을 사용하기 위해 OneDrive를 설치합니다. 도움말은 [조건부 액세스 배포](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) 계획을 참조합니다.
