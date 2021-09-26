---
title: Microsoft 365 관리 센터의 Intune 관리자 역할 정보
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
description: 관리자 역할은 비즈니스 기능에 매핑되며 관리 센터에서 특정 작업을 수행할 수 있는 권한을 부여합니다. 예를 들어 서비스 관리자는 Microsoft로 지원 티켓을 엽니다.
ms.openlocfilehash: c5aaa27dee2aea6ea1c8383a0a729a7bd0465f8b
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "59773478"
---
# <a name="intune-admin-roles-in-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터의 Intune 관리자 역할

Microsoft 365 또는 Office 365 구독은 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>를 사용해 조직의 사용자에게 할당할 수 있는 관리자 역할 집합과 함께 제공됩니다. 각 관리자 역할은 일반적인 비즈니스 기능에 해당하며, 조직의 구성원에게 관리 센터에서 특정 작업을 수행할 수 있는 권한을 부여합니다.

Microsoft 365 관리 센터를 통해 일부 Microsoft Intune 역할을 관리할 수 있습니다. 그러나 해당 역할은 Intune 관리 센터에서 사용할 수 있는 역할의 하위 집합입니다. Microsoft Intune에 대한 자세한 역할 설명을 찾고 있나요? [Microsoft Intune으로 RBAC(역할 기반 액세스 제어)](/mem/intune/fundamentals/role-based-access-control)를 확인하세요.

<a href="https://go.microsoft.com/fwlink/p/?linkid=2097861" target="_blank">Microsoft 365 관리 센터</a>에서 역할을 할당하는 방법에 대한 자세한 내용은 [관리자 역할 할당](assign-admin-roles.md)을 참조하세요.

Microsoft 365 관리 센터에서 **역할** 로 이동한 다음 아무 역할이나 선택하여 세부 정보 창을 열 수 있습니다. **사용 권한** 탭을 선택하여 해당 역할에 할당된 관리자가 수행할 수 있는 작업에 대한 자세한 목록을 볼 수 있습니다. 역할에 사용자를 추가하려면 **할당된** 또는 **할당된 관리자** 탭을 선택합니다.

## <a name="microsoft-intune-roles-available-in-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터에서 이용 가능한 Microsoft Intune 역할

|관리자 역할     |이 역할에는 누가 할당되어야 하나요?  |
|---------|---------|
|응용 프로그램 관리자     |   모바일 앱의 응용 프로그램 수명 주기를 관리하고, 정책 관리 앱을 구성하고, 장치 정보와 구성 프로필을 보는 사용자에게 응용 프로그램 역할을 할당합니다.  |
|지원 센터 운영자     |   사용자와 장치에 앱과 정책을 할당하는 사용자에게 지원 센터 운영자 역할을 할당합니다. |
|Intune 역할 관리자    |   Intune 사용 권한을 다른 관리자에게 할당할 수 있고 사용자 지정 및 기본 제공 Intune 역할을 관리할 수 있는 사용자에게 Intune 역할 관리자를 할당합니다.   |
|정책 및 프로필 관리자     |   규정 준수 정책, 구성 프로필, Apple 등록을 관리하는 사용자에게 정책 및 프로필 관리자 역할을 할당합니다.   |
|읽기 전용 운영자     |   사용자, 장치, 등록 세부 정보 및 구성을 보기만 할 수 있는 사용자에게 읽기 전용 운영자 역할을 할당합니다.   |
|학교 관리자     |   교육용 Intune에서 Windows 10 및 iOS 장치, 앱과 구성을 관리하는 데 필요한 모든 액세스 권한을 부여하려면 학교 관리자 역할을 사용자에게 할당합니다.   |

## <a name="delegated-administration-for-microsoft-partners"></a>Microsoft 파트너를 위한 위임 된 관리

Microsoft 파트너와 함께 업무를 진행하는 경우에는 파트너에게 관리자 역할을 할당할 수 있습니다. 파트너 또한 사용자 회사 또는 파트너 회사의 사용자들에게 관리자 역할을 할당할 수 있습니다. 예를 들어 파트너가 대신 사용자의 온라인 조직을 설정하고 관리하는 경우 이 기능이 필요할 수 있습니다.
  
파트너는 다음과 같은 역할을 할당할 수 있습니다. 
  
- 파트너 센터를 통해 다단계 인증을 관리하는 것을 제외하고는 전역 관리자와 동등한 권한을 가진 전체 관리 기능

- 헬프데스크 관리자와 동일한 권한을 가진 제한된 관리 기능

파트너가 이러한 역할을 사용자에게 할당하기 전에 파트너를 사용자 계정에 위임된 관리자로 추가해야 합니다. 이 프로세스는 공인 파트너가 시작 합니다. 파트너는 사용자가 파트너에게 위임된 관리자 역할을 수행할 권한을 부여할 것인지 묻는 전자 메일을 보냅니다. 안내 사항은 [파트너 관계 승인 또는 제거](../misc/add-partner.md)를 참조하십시오.
  
## <a name="related-content"></a>관련 콘텐츠

[Microsoft 365 관리자 역할 정보](about-admin-roles.md)(문서)\
[관리자 역할 할당](assign-admin-roles.md)(문서)\
[Microsoft 365 관리 센터의 활동](../activity-reports/activity-reports.md)(문서)