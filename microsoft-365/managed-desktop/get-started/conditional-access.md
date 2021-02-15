---
title: 등록 후 설정 수정
description: 특정 Microsoft 계정을 제외하는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ca919798480698f92bba094c3755b3eccce30888
ms.sourcegitcommit: c1f9a1b2a34146c51c9e33c4119a388b249ce7a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2021
ms.locfileid: "49867973"
---
# <a name="adjust-settings-after-enrollment"></a>등록 후 설정 수정

Microsoft Managed Desktop에서 등록을 완료한 후 일부 관리 설정을 조정해야 할 수 있습니다. 필요한 경우 확인하고 조정하려면 다음 단계를 수행합니다.

1. 다음 섹션에서 설명하는 Microsoft Intune 및 Azure Active Directory 설정을 검토합니다.
2. 환경에 항목이 적용되는 경우 설명된 항목을 조정합니다.
3. 모든 설정이 올바른지 다시 확인하려면 준비 평가 도구를 [](https://aka.ms/mmdart) 다시 실행하여 Microsoft Managed Desktop과 충돌하지 않습니다.

> [!NOTE]
> 다음 달에 작업을 계속할 때 Microsoft Intune, Azure Active Directory 또는 Microsoft 365에서 Microsoft Managed Desktop에 영향을 주는 정책에 등록한 후 변경하는 경우 Microsoft Managed Desktop이 제대로 작동하지 않을 수 있습니다. 서비스 관련 문제를 방지하려면 준비 평가 [](../get-ready/readiness-assessment-fix.md) 도구에서 찾은 문제 해결에 설명된 특정 설정을 확인한 후 여기에 나열된 정책을 변경합니다. 준비 평가 도구를 다시 실행하면 됩니다.


## <a name="microsoft-intune-settings"></a>Microsoft Intune 설정

- Autopilot 배포 프로필: Autopilot 정책을 사용하는 경우 각 정책을 업데이트하여 최신 작업 공간 장치 **-All** Azure AD 그룹을 제외합니다. 업데이트하려면 배정  아래에 있는 제외된 그룹 섹션에서 Microsoft Managed Desktop 등록 중에 만들어진 최신 작업 공간 장치 **-모든** Azure AD 그룹을 선택합니다.  Microsoft Managed Desktop은 이름(최신 Workplace Autopilot 프로필)에 "최신 작업 공간"이 있는 Autopilot 프로필도 **만들게 됩니다.** 자체 Autopilot 프로필을 업데이트할 때 Microsoft  Managed Desktop에서 만든 최신 Workplace **Autopilot 프로필에서** 최신 작업 공간 장치 **-모든** Azure AD 그룹을 제외하지 않는지 확인하세요.

- 조건부 액세스 정책: Microsoft Managed Desktop 등록 후 Azure AD, Microsoft Intune 또는 끝점용 Microsoft Defender와 관련된 새 조건부 액세스 정책을 만드는 경우 최신 **Workplace Service Accounts** Azure AD 그룹을 제외합니다. 단계는 조건부 [액세스: 사용자 및 그룹을 참조하세요.](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups) Microsoft Managed Desktop은 이러한 계정에 대한 액세스를 제한하기 위해 별도의 조건부 액세스 정책을 유지 관리합니다. Microsoft Managed Desktop 조건부 액세스 **정책(최신** 작업 공간 - 보안 작업 공간)을 검토하기 위해 Microsoft 끝점 관리자로 이동하여 **Endpoint Security에서** **조건부 액세스로** 이동합니다. 이름에 "최신 작업 공간"이 있는 Microsoft Managed Desktop에서 만든 Azure AD 조건부 액세스 정책을 수정하지 않습니다.

- 다단계 인증: Microsoft Managed Desktop 등록 후 Azure AD, Intune 또는 끝점용 Microsoft Defender와 관련된 조건부 액세스 정책에서 새로운 다단계 인증 요구 사항을 만드는 경우 최신 **Workplace Service 계정** Azure AD 그룹을 제외합니다. 단계는 조건부 [액세스: 사용자 및 그룹을 참조하세요.](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups) Microsoft Managed Desktop은 이 그룹의 구성원에 대한 액세스를 제한하기 위해 별도의 조건부 액세스 정책을 유지 관리합니다. Microsoft Managed Desktop 조건부 액세스 정책(최신 작업 공간 **) 을** 검토하기 위해 Microsoft Endpoint Manager로 이동하여 **Endpoint Security에서** **조건부 액세스로** 이동합니다. 

- Windows 10 업데이트 링: 만든 Windows 10 업데이트 링 정책의 경우 각 정책에서 최신 **Workplace Devices -All** Azure AD 그룹을 제외합니다. 단계는 업데이트 [링 만들기 및 할당을 참조하세요.](https://docs.microsoft.com/mem/intune/protect/windows-10-update-rings#create-and-assign-update-rings) Microsoft Managed Desktop은 일부 업데이트 링 정책도 만들며, 모든 정책은 이름(예: 최신 작업 공간 업데이트 정책 **[광범위],** 최신 작업 공간 업데이트 정책 **[Fast],** 최신 작업 공간 업데이트 정책 **[첫 번째]** 및 최신 작업 공간 업데이트 정책 **[테스트]))에**"최신 작업 공간"이 있습니다. 자체 정책을 업데이트할 때 Microsoft  Managed Desktop에서 만든 그룹에서 최신 작업 공간 장치 **-모든** Azure AD 그룹을 제외하지 않는지 확인하세요.


## <a name="azure-active-directory-settings"></a>Azure Active Directory 설정

셀프 서비스 암호 재설정: 모든 사용자에 대해 셀프 서비스 암호 재설정을 사용하는 경우 할당을 조정하여 Microsoft Managed Desktop 서비스 계정을 제외합니다. 이 할당을 조정하기 위해 *Microsoft* Managed Desktop 서비스 계정을 제외한 모든 사용자에 대해 Azure AD 동적 그룹을 만든 다음 "모든 사용자" 대신 해당 그룹을 할당에 사용합니다.

서비스 계정을 찾고 제외할 수 있도록 사용할 수 있는 동적 쿼리의 예는 다음과 같습니다.

```Console
(user.objectID -ne null) and (user.userPrincipalName -ne "MSADMIN@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSADMININT@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_SOC_RO@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_WDGSOC@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSTEST@TENANT.onmicrosoft.com")
```

이 쿼리에서 테넌트 @TENANT 이름으로 대체합니다.



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft Managed Desktop을 시작하기 위한 단계

1. [관리 포털에서 관리자 연락처 추가 및 확인](add-admin-contacts.md)
2. 등록 후 설정 조정(이 문서)
3. [라이선스 할당](assign-licenses.md)
4. [Intune 회사 포털 배포](company-portal.md)
5. [엔터프라이즈 상태 로밍 사용](enterprise-state-roaming.md)
6. [장치 설정](set-up-devices.md)
7. [사용자들이 장치를 사용할 수 있도록 준비시키기](get-started-devices.md)
8. [앱 배포](deploy-apps.md)
