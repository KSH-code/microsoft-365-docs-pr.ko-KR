---
title: 관리 포털에서 관리자 연락처 추가 및 확인
description: 각 포커스 영역에 대해 문의할 사람을 알려주십시오.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 3f77a5f6f0af83ea82d2ab3cea0798b95e27c2d2
ms.sourcegitcommit: 3d37043c0447359c952dc99026c219dd69f6fb8d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2019
ms.locfileid: "38012069"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a>관리 포털에서 관리자 연락처 추가 및 확인

Microsoft Managed Desktop service가 고객과 통신 하는 방법에는 여러 가지가 있습니다. 통신을 합리화 하 고 적절 한 사용자가 확인 하는 일이 없도록 하려면 관리자 연락처 집합을 제공 해야 합니다. Microsoft Managed Desktop IT 작업에서는 해당 사용자에 게 연락 하 여 테 넌 트에 대 한 문제 해결 문제가 있을 수 있습니다.

> [!IMPORTANT]
> 관리자 포털에서 이러한 연락처를 이미 추가 했을 수 있습니다. 이 경우 심각한 사고가 발생 하는 경우 Microsoft Managed Desktop이 연락할 수 **있어야** 하므로 연락처 목록이 정확한 지 확인 하는 것이 좋습니다.

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Microsoft Managed Desktop Admin 포털에 대 한 Azure Active Directory 액세스

Microsoft Managed Desktop Administration portal을 사용 하려면 포털에 액세스 하는 사용자에 게 다음 Azure AD (Active Directory) 역할 중 하나가 있어야 합니다.
- 전역 관리자
- Intune 서비스 관리자
- 대금 청구 관리자
- 서비스 지원 관리자

전역 관리자는 Microsoft Managed Desktop에서 조직을 등록할 사용자 여야 합니다. 관리 포털 내에서 모든 5 개의 역할이 동일한 액세스 권한을 가지 며 작업을 시작 하 고 확인할 수 있습니다. Azure AD에서 이러한 역할을 할당 하는 방법에 대 한 자세한 내용은 [Azure Active Directory에서 관리자 역할 권한을](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)참조 하세요. 

## <a name="admin-contact-areas-of-focus"></a>포커스의 관리자 연락처 영역

관리자 연락처는 질문에 답하고 각 영역에 대 한 의사 결정을 내릴 수 있는 가장 좋은 사용자나 그룹 이어야 합니다. **Microsoft Managed Desktop 작업은 해당 관리자 연락처에 연락 하 여 고객의 지원 요청을 포함 하는 질문을 제공 합니다.** 이러한 관리 연락처는 지원 요청 업데이트 및 새 메시지에 대 한 알림을 받습니다. 이러한 영역은 다음과 같습니다.

포커스 영역 | 에 대 한 질문
--- | ---
앱 패키징 | 앱 패키징 문제 해결
장치 | 장치 상태, Microsoft Managed Desktop devices 문제 해결
보안 | Microsoft Managed Desktop 장치에 대 한 보안 문제 해결
IT 지원 센터 | 지원 직원이 Microsoft 관리 되는 데스크톱 지원 영역을 벗어나는 최종 사용자 티켓을 사용 하는 경우 
기타 | 다른 영역에 포함 되지 않는 문제의 경우

**이러한 연락처에 대해 선택한 사람은 Microsoft Managed Desktop 환경에 대 한 의사 결정을 내리는 데 필요한 지식과 권한을가지고 있어야 합니다.** Microsoft Managed Desktop environment를 온보드 하면 로컬 헬프데스크 및 보안에 대 한 연락처를 추가 하 라는 메시지가 표시 됩니다. 

[지원 요청을 제출](../working-with-managed-desktop/support.md)하는 경우 관리자 연락처가 필요 합니다. 지원 요청의 포커스 영역에 대 한 관리자 연락처가 있어야 합니다. 

**관리자 연락처를 추가 하려면**

1.  [Microsoft Managed 데스크톱 관리 포털](https://aka.ms/mwaasportal)에 로그인 합니다. 

2.  **지원**에서 **관리자 연락처**를 선택 합니다. 

    ![지원 메뉴, 관리자 연락처](images/admincontacts.png)

3. **추가**를 선택 합니다.

    ![관리 포털 추가 단추](images/adminadd.png)

4.  **포커스 영역** 을 선택 하 고 연락처에 대 한 정보를 입력 합니다. 

    ![포커스 영역 목록](images/areaoffocus.png)

5. 포커스의 각 영역에 대해 반복 합니다. 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft Managed Desktop을 시작 하기 위한 단계

1. 관리자 포털에서 관리자 연락처 추가 및 확인 (이 항목)
2. [조건부 액세스 조정](conditional-access.md)
3. [라이선스 할당](assign-licenses.md)
4. [장치에 Intune 회사 포털 설치](company-portal.md)
5. [엔터프라이즈 상태 로밍 사용](enterprise-state-roaming.md)
6. [Microsoft Managed Desktop 장치 설정](set-up-devices.md)
7. [사용자들이 장치를 사용할 수 있도록 준비시키기](get-started-devices.md)
8. [장치에 앱 배포](deploy-apps.md)