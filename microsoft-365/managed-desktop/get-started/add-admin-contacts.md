---
title: 관리 포털에서 관리자 연락처 추가 및 확인
description: 각 중점 영역에 대해 누구에게 연락해야 하는지 알려주세요.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 18823db8ca8d4bfa82b8ab6265ee8a0902a13e79
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925895"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a>관리 포털에서 관리자 연락처 추가 및 확인

Microsoft Managed Desktop 서비스가 고객과 소통하는 방법에는 여러 가지가 있습니다. 의사 소통이 원활하고 올바른 사용자에게 확인하고 있는지 확인하려면 관리자 연락처 집합을 제공해야 합니다. Microsoft Managed Desktop IT 운영팀에서 이 사용자들에게 연락하여 테넌트에 대한 문제 해결에 대한 도움을 줄 것입니다.

> [!IMPORTANT]
> 관리자 포털에서 이미 이 연락처를 추가했을 수 있습니다. 이 경우에는 심각한 문제가 발생할 경우 Microsoft Managed Desktop이 연락할 수 **있어야** 하기 때문에 연락처 목록이 정확한지 다시 한 번 확인하세요.

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Microsoft Managed Desktop 관리 포털에 대한 Azure Active Directory 액세스

Microsoft Managed Desktop 관리 포털을 사용하려면 포털에 액세스 하는 사용자가 다음 Azure AD(Active Directory) 역할 중 하나를 보유해야 합니다.
- 전역 관리자
- Intune 서비스 관리자
- 전역 읽기 권한자
- 서비스 지원 관리자

전역 관리자는 Microsoft Managed Desktop에 조직을 등록해야 합니다. 모든 5개 역할은 관리자 포털에서 동일한 액세스 권한을 가지며 작업을 시작하고 볼 수 있습니다. Azure AD에서 역할을 할당하는 방법에 대한 자세한 내용은 [Azure Active Directory에서 관리자 역할 사용 권한](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)을 참조하세요. 

## <a name="admin-contact-areas-of-focus"></a>관리자 연락처 포커스 영역

관리자 연락처는 질문에 답하고 다양한 중점 영역에 대한 의사 결정을 내릴 수 있는 최고의 사용자나 그룹이어야 합니다. **Microsoft Managed Desktop 운영팀이 이러한 관리자 연락처에 연락하여 고객이 제출한 지원 요청과 관련된 질문을 할 수 있습니다.** 이 관리자 연락처는 지원 요청 업데이트와 새 메시지에 대한 알림을 받습니다. 해당 영역은 다음과 같습니다.

포커스 영역 | 관련 질문
--- | ---
앱 패키징 | 앱 패키징 문제 해결
장치 | 장치 상태, Microsoft Managed Desktop 장치를 사용하여 문제 해결
보안 | Microsoft Managed Desktop 장치를 사용하여 보안 문제 해결
IT 지원 센터 | 지원 직원이 지원 영역 외부에서 사용자 티켓을 Microsoft Managed Desktop 경우 
기타 | 다른 영역에서 다루지 않는 문제

**이러한 연락처로 선택한 사용자는 Microsoft Managed Desktop 환경을 결정할 수 있는 지식과 권한이 있어야 합니다.** Microsoft Managed Desktop 환경을 온보드하는 경우 로컬 지원 센터 및 보안에 대한 연락처를 추가하라는 메시지가 표시됩니다. 

[지원 요청을 제출](../service-description/support.md)하는 경우 관리자 연락처가 필요합니다. 지원 요청의 포커스 영역에 대한 관리자에게 문의해야 합니다. 

**관리자 연락처 추가하기**

1.  [Microsoft Managed Desktop 관리 포털](https://aka.ms/mwaasportal)에 로그인합니다. 

2.  **지원** 에서 **관리자 연락처** 를 선택합니다. 

    ![지원 메뉴, 상단 근처에서 선택된 관리자 연락처](../../media/admincontacts.png)

3. **추가** 를 선택하세요.

    ![내보내기 및 새로 고침 왼쪽에 관리 포털, 추가 단추](../../media/adminadd.png)

4.  **포커스 영역** 을 선택하고 연락처에 대한 정보를 입력합니다. 

    ![기타, 앱 및 보안과 같은 포커스 영역 목록](../../media/areaoffocus.png)

5. 각 포커스가 영역에 대해 반복합니다. 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft Managed Desktop을 시작하기 위한 단계

1. 관리 포털에서 관리자 연락처 추가 및 확인(이 항목)
2. [조건부 액세스 조정](conditional-access.md)
3. [라이선스 할당](assign-licenses.md)
4. [장치에 Intune 회사 포털 설치](company-portal.md)
5. [엔터프라이즈 상태 로밍 사용](enterprise-state-roaming.md)
6. [Microsoft Managed Desktop 장치 설정](set-up-devices.md)
7. [사용자들이 장치를 사용할 수 있도록 준비시키기](get-started-devices.md)
8. [장치에 앱 배포](deploy-apps.md)