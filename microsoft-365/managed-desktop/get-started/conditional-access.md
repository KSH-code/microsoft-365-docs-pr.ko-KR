---
title: 등록 후 설정 조정
description: 특정 Microsoft 계정을 제외 하는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 76a73372cc7517c3241390e58c28b0b02bffd664
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527700"
---
# <a name="adjust-settings-after-enrollment"></a>등록 후 설정 조정

Microsoft Managed Desktop의 등록을 완료 한 후에는 특정 Microsoft Intune 및 azure AD (Active Directory) 설정을 조정 하 여 관리를 허용 하 고 보안을 유지 해야 합니다. Microsoft Managed Desktop 장치 및 사용자가 포함 된 Azure AD 그룹을 제외 하려면 다음 설정을 설정 합니다. 그룹을 제외 하는 단계에 대 한 자세한 내용은 [조건부 액세스: 사용자 및 그룹](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users)을 참조 하십시오.

## <a name="microsoft-intune-settings"></a>Microsoft Intune 설정

- Autopilot 배포 프로필: **최신 작업 공간 장치 (모든**  Azure AD 그룹)를 제외 합니다. 자세한 단계는 [Windows Autopilot을 사용 하 여 Intune에서 windows 장치 등록](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)을 참조 하십시오.
- 조건부 액세스 정책: **최신 작업 공간 서비스 계정** Azure AD 그룹을 제외 합니다. 단계에 대 한 자세한 내용은 [조건부 액세스: 사용자 및 그룹](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)을 참조 하십시오.
- 다단계 인증: 다단계 인증을 필요로 하는 모든 조건부 액세스 정책이 **최신 작업 공간 서비스 계정** Azure AD 그룹을 제외 하는지 확인 합니다. 자세한 내용은 [조건부 액세스 정책](../get-ready/readiness-assessment-fix.md#conditional-access-policies) 및 [조건부 액세스: 모든 사용자에 대해 MFA 필요](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)를 참조 하세요.
- 보안 기준: **최신 작업 공간 장치 (All**  Azure AD 그룹)를 제외 합니다. 자세한 단계는 [security 기준선이 Use To Windows 10 devices In Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines)을 참조 하십시오.
- Windows 10 업데이트 링: **최신 작업 공간 장치 (모든**  Azure AD 그룹)를 제외 합니다. 자세한 단계는 [Intune에서 Windows 10 소프트웨어 업데이트 관리](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)를 참조 하세요.


## <a name="azure-active-directory-settings"></a>Azure Active Directory 설정

셀프 서비스 암호 재설정: **선택한** 설정을 선택한 다음 **최신 작업 공간 장치-모든** Azure AD 그룹을 선택 합니다. 자세한 내용은 [Tutorial: 사용자가 Azure Active Directory 셀프 서비스 암호 재설정을 사용 하 여 계정의 잠금을 해제 하거나 암호를 재설정할 수 있도록](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)합니다 .를 참조 하세요.



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft Managed Desktop을 시작하기 위한 단계

1. [관리 포털에서 관리자 연락처 추가 및 확인](add-admin-contacts.md)
2. 등록 후 설정 조정 (이 문서)
3. [라이선스 할당](assign-licenses.md)
4. [Intune 회사 포털 배포](company-portal.md)
5. [엔터프라이즈 상태 로밍 사용](enterprise-state-roaming.md)
6. [장치 설정](set-up-devices.md)
7. [사용자들이 장치를 사용할 수 있도록 준비시키기](get-started-devices.md)
8. [앱 배포](deploy-apps.md)
