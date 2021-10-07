---
title: 준비 평가 도구
description: 두 도구, 실행 검사 및 결과의 의미에 대해 설명
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: c584632a625ecb8597aa0c9319063e6f9198bec3
ms.sourcegitcommit: afee35210f8d68a7f20676ff2a829464b0b0adb2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2021
ms.locfileid: "60216937"
---
# <a name="readiness-assessment-tools"></a>준비 평가 도구

응용 프로그램에 등록할 때 가능한 Microsoft Managed Desktop 설정 및 기타 매개 변수와 미리 설정해야 하는 특정 장치 및 네트워크 요구 사항이 있습니다. 관리 포털을 통해 액세스하는 Microsoft Managed Desktop 관리 관련 설정을 확인합니다. 다운로드 가능한 다른 도구는 개별 장치 요구 사항 및 네트워크 설정을 확인합니다. 이러한 도구를 사용하여 이러한 설정을 확인하고 올바른 설정이 아닌 설정을 수정하기 위한 자세한 단계를 받을 수 있습니다.

## <a name="downloadable-readiness-assessment-checker-for-devices-and-network"></a>장치 및 네트워크에 대한 다운로드 가능한 준비 평가 검사

다운로드 가능한 준비 평가 검사기 사용에 대한 자세한 내용은 다운로드 가능한 준비 평가 검사 를 [참조합니다.](readiness-assessment-downloadable.md)

## <a name="online-readiness-assessment-tool-for-management-settings"></a>관리 설정을 위한 온라인 준비 평가 도구

온라인 [도구는](https://aka.ms/mmdart) Microsoft Endpoint Manager(특히 Microsoft Intune), Azure Active Directory(Azure AD) 및 Microsoft 365 설정이 Microsoft Managed Desktop. Microsoft Managed Desktop Azure AD 조직(테넌트)에서 검사를 마지막으로 실행한 후 12개월 동안 이러한 검사와 관련된 데이터가 보존됩니다. 12개월 후에 비식별된 양식으로 보존됩니다. 수집하는 데이터를 삭제할 수 있습니다.

전역 읽기 권한자 또는 Intune 관리자 역할이 있는 모든 사용자가 이 도구를[](readiness-assessment-fix.md#conditional-access-policies) 실행할 수 있지만 [](readiness-assessment-fix.md#multifactor-authentication) 조건부 액세스 정책 및 다단계 인증의 두 가지 확인에는 추가 권한이 필요합니다.

> [!IMPORTANT]  
> 온라인 준비 평가 도구를 사용하면 처음으로 온라인 준비 Microsoft Managed Desktop 준비를 확인할 수 있습니다. 조직이 이미 조직에 Microsoft Managed Desktop 이 도구를 사용하지 않습니다.

평가 도구는 다음 항목을 검사합니다.

## <a name="microsoft-intune-settings"></a>Microsoft Intune 설정

|수표  |설명  |
|---------|---------|
|Autopilot 배포 프로필     | Autopilot 배포 프로필 할당이 모든 장치에 적용되지 않는지 확인(프로필을 모든 디바이스에 Microsoft Managed Desktop 않습니다.)        |
|인증서 커넥터     | 인증서 커넥터의 상태를 확인하여 커넥터가 활성 상태인지 확인   |
|조건부 액세스     | 조건부 액세스 정책이 모든 사용자에게 할당되지 않았는지  확인(조건부 액세스 정책을 서비스 계정에 Microsoft Managed Desktop 않습니다.)    |
|장치 준수 정책     | Intune 규정 준수 정책이 모든 사용자에게 할당되지  않는지 검사합니다(정책은 모든 사용자 장치에 Microsoft Managed Desktop 않습니다.)    |
|장치 구성 프로필     | 구성 프로필이 모든 사용자 또는 모든 장치에 할당되지 않는지  확인(구성 프로필을 모든 Microsoft Managed Desktop 않습니다.)     |
|장치 유형 제한     | 조직의 Windows 10 Intune에 등록할 수 있는 장치 확인        |
|등록 상태 페이지     | 등록 상태 페이지를 사용할 수 없는지 확인      |
|Intune 등록     | Azure AD Windows 10 디바이스가 Intune에 자동으로 등록되어 있는지 확인         |
|비즈니스용 Microsoft Store     | Intune과 비즈니스용 Microsoft Store 활성화 및 동기화가 가능한지 확인        |
|다단계 인증 | 서비스 계정에 다단계 인증이 적용되지 Microsoft Managed Desktop 않습니다.
|PowerShell 스크립트     | 모든 Windows PowerShell 대상이 될 수  있는 방식으로 Microsoft Managed Desktop 확인    |
|지역     | 사용자 지역이 지원되는지 Microsoft Managed Desktop        |
|보안 기준     | 보안 기준 프로필이 모든 사용자 또는 모든 장치를 대상으로 하지 않는지  검사합니다(보안 기준 정책은 모든 Microsoft Managed Desktop 않습니다.)       |
|Windows 앱     | 디바이스에 할당할 앱 Microsoft Managed Desktop 검토      |
|비즈니스용 Windows Hello     | 비즈니스용 Windows Hello 사용하도록 설정되어 있는지 확인        |
|Windows 10 업데이트 링     | Intune의 "Windows 10 업데이트 링" 정책이 모든 사용자 또는 모든 장치를 대상으로  하지 않는지 검사합니다(정책이 모든 Microsoft Managed Desktop 대상이 아니야 합니다.)     |


## <a name="azure-active-directory-settings"></a>Azure Active Directory 설정

|수표  |설명  |
|---------|---------|
|Enterprise 상태 로밍에 대한 "Enterprise" 구독     | "false"로 설정하면 상태 로밍이 제대로 작동하지 Enterprise 수 있는 설정을 검사하는 방법을 알 수 있습니다.  |
|Enterprise State Roaming     | 상태 로밍이 사용하도록 설정되어 Enterprise 방법을 알 수 있습니다.       |
|라이선스     | 필요한 라이선스를 획득한지 [확인](prerequisites.md#more-about-licenses)         |
|다단계 인증     | 모든 사용자에게 다단계 인증이 적용되지 않는지 확인(다단계 인증을 서비스 계정에 실수로 Microsoft Managed Desktop 않습니다.)|
|보안 계정 이름   | 사용자 이름이 자체적으로 사용하기 위해 예약된 Microsoft Managed Desktop 이름이 없는지 확인        |
|보안 관리자 역할     | 보안 읽기 사용자, 보안 운영자 또는 전역 독자 역할이 있는 사용자에게 끝점용 Microsoft Defender에서 해당 역할이 할당되어 있는지 확인         |
|보안 기본값 | Azure AD 조직에서 보안 기본값을 사용하도록 설정되어 있는지 Azure Active Directory |
|셀프 서비스 암호 재설정     | 셀프 서비스 암호 재설정이 사용하도록 설정되어 있는지 확인        |
|표준 사용자 역할     | 사용자가 표준 사용자로서 로컬 관리자 권한이 없는지 확인         |


## <a name="microsoft-365-apps-for-enterprise-settings"></a>엔터프라이즈용 Microsoft 365 앱 설정

|수표  |설명  |
|---------|---------|
|비즈니스용 OneDrive     | 지원되지 비즈니스용 OneDrive 설정이 사용 중인지 확인합니다.        |


각 검사에 대해 도구는 다음 네 가지 결과 중 하나를 보고합니다.


|결과  |의미  |
|---------|---------|
|준비     | 등록을 완료하기 전에 필요한 작업은 없습니다.        |
|권고    | 등록과 사용자에 대해 최상의 환경을 제공하려면 도구의 단계를 따르세요. *등록을* 완료할 수 있지만 첫 번째 장치를 배포하기 전에 이러한 문제를 해결해야 합니다.        |
|준비되지 않음 | *이러한 문제를* 해결하지 않는 경우 등록이 실패합니다. 도구의 단계에 따라 문제를 해결합니다.        |
|오류 | 사용중인 Azure AD(Active Director) 역할에 이 검사를 실행할 수 있는 권한이 없습니다. |

## <a name="after-enrollment"></a>등록 후

등록을 완료한 Microsoft Managed Desktop 돌아가서 특정 Intune 및 Azure AD 설정을 조정해야 합니다. 자세한 내용은 등록 후 [설정 조정을 참조하세요.](../get-started/conditional-access.md)

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>준비 단계 Microsoft Managed Desktop

1. [Microsoft Managed Desktop의 필수 구성 요소](prerequisites.md)를 감토하세요.
2. 준비 평가 도구를 실행합니다(이 문서).
1. [회사 포털](../get-started/company-portal.md)을 구입하세요.
1. [게스트 계정에 대한 필수 구성 요소](guest-accounts.md)를 검토합니다.
1. [네트워크 구성](network.md)을 확인합니다.
1. [인증서 및 네트워크 프로필을 준비](certs-wifi-lan.md)합니다.
1. [데이터에 대한 사용자 액세스를 준비](authentication.md)합니다.
1. [앱을 준비](apps.md)합니다.
1. [매핑된 드라이브를 준비](mapped-drives.md)합니다.
1. [인쇄 리소스를 준비](printing.md)합니다.
1. [장치 이름](address-device-names.md)을 기입합니다.
