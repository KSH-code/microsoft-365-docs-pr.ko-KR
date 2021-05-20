---
title: Office 스크립트 설정 관리
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: 조직의 사용자에 대한 Office 스크립트 설정을 관리하는 방법을 알아보세요.
ms.openlocfilehash: e0cb52c4a8f48ff2310c83ffce61e08a0236ed59
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572312"
---
# <a name="manage-office-scripts-settings"></a>Office 스크립트 설정 관리

[Office 스크립트를](/office/dev/scripts)사용하면 웹에서 Excel 스크립트를 녹화, 편집 및 실행하여 작업을 자동화할 수 있습니다. Office 스크립트는 Power Automate 함께 작동하며 사용자는 Excel 온라인(비즈니스) 커넥터를 사용하여 통합 문서에서 스크립트를 실행합니다. Microsoft 365 관리자는 Microsoft 365 관리자 센터에서 Office 스크립트 설정을 관리할 수 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

- Office 스크립트 설정을 관리하려면 글로벌 관리자여야 합니다. 자세한 내용은 [관리자 역할 정보](../add-users/about-admin-roles.md)중을 참조하십시오.

- 조직의 사용자가 다음 계획 중 하나와 같은 Office 데스크톱 앱에 대한 액세스를 포함하는 Microsoft 365 또는 Office 365 상업용 또는 EDU 계획에 대한 유효한 라이선스를 가지고 있는지 확인합니다.

    - Microsoft 365 Business Standard
    - 비즈니스용 Microsoft 365 앱
    - 엔터프라이즈용 Microsoft 365 앱
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>Office 스크립트의 가용성 관리 및 스크립트 공유

1. Microsoft 365 관리 센터에서 **설정** \> **조직 설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">서비스</a> 탭으로 이동합니다.

2. **Office 스크립트를 선택합니다.**

3. Office 스크립트는 기본적으로 켜져 있으며 조직의 모든 사용자가 기능에 액세스하여 사용하고 스크립트를 공유할 수 있습니다. 조직에 대한 스크립트Office 끄려면 사용자가 **확인란에서 작업을 자동화할 웹용 Excel** 있습니다.

4. 이전에 조직에 대한 스크립트Office를 끄고 다시 켜려면 **사용자가 웹용 Excel 작업을 자동화한** 다음 기능에 액세스하고 사용할 수 있는 사용자를 지정합니다.

    - 조직의 모든 사용자가 Office 스크립트에 액세스하고 사용할 수 있도록 하려면 모든 사람(기본값)을 선택해제합니다. 

    - 특정 그룹의 구성원만 Office 스크립트에 액세스하고 사용할 수 있도록 하려면 **특정 그룹을** 선택한 다음 그룹의 이름이나 이메일 별칭을 입력하여 허용 목록에 추가합니다. 허용 목록에 하나의 그룹만 추가할 수 있으며 다음 유형 중 하나여야 합니다.
        - Microsoft 365 그룹
        - 배포 그룹
        - 보안 그룹
        - 메일 사용 가능 보안 그룹
    
        다양한 유형의 그룹에 대해 자세히 알아보려면 [그룹 비교를](../create-groups/compare-groups.md)참조하십시오.

5. 스크립트에 Office 액세스할 수 있는 사용자가 조직의 다른 사용자와 스크립트를 공유할 수 있도록 **하려면 Office 스크립트에 액세스할 수 있는 사용자가 조직의 다른 사용자와 스크립트를 공유하도록** 합니다. 조직 외부의 스크립트를 공유하는 것은 허용되지 않습니다.
 
    > [!NOTE]
    > 나중에 조직에 대한 스크립트 공유를 해제하면 사용자는 이전에 공유된 스크립트를 계속 실행할 수 있습니다.
 
6. 스크립트에 액세스할 수 Office 있는 사용자를 지정합니다.
    
    - Office 스크립트에 액세스할 수 있는 모든 사용자가 스크립트를 공유할 수 있도록 하려면 모든 사용자(기본값)를 선택해제합니다. 

    - 스크립트에 액세스할 Office 액세스할 수 있는 특정 그룹의 구성원만 스크립트를 공유할 수 있도록 하려면 **특정 그룹을** 선택한 다음 그룹의 이름 또는 이메일 별칭을 입력하여 허용 목록에 추가합니다. 허용 목록에 하나의 그룹만 추가할 수 있으며 다음 유형 중 하나여야 합니다.
        - Microsoft 365 그룹
        - 배포 그룹
        - 보안 그룹
        - 메일 사용 가능 보안 그룹
    
        다양한 유형의 그룹에 대해 자세히 알아보려면 [그룹 비교를](../create-groups/compare-groups.md)참조하십시오.

7. 사용자가 Power Automate 흐름 내에서 Office 스크립트를 실행할 수 있도록 하려면 **Office 스크립트에 액세스할 수 있는 사용자가 Power Automate 스크립트를 실행하도록 선택합니다.** 이를 통해 사용자는 [Excel 온라인(비즈니스) 커넥터의](/connectors/excelonlinebusiness) **실행 스크립트** 옵션으로 흐름 단계를 추가할 수 있습니다.

    - 스크립트에 액세스할 수 Office 있는 모든 사용자가 흐름에서 스크립트를 사용하도록 허용하려면 모든 사람(기본값)을 선택합니다. 

    - 스크립트에 액세스할 수 Office 특정 그룹의 구성원만 흐름에서 스크립트를 사용하도록 허용하려면 **특정 그룹을** 선택한 다음 그룹의 이름 또는 이메일 별칭을 입력하여 허용 목록에 추가합니다. 허용 목록에 하나의 그룹만 추가할 수 있으며 다음 유형 중 하나여야 합니다.
        - Microsoft 365 그룹
        - 배포 그룹
        - 보안 그룹
        - 메일 사용 가능 보안 그룹

        다양한 유형의 그룹에 대해 자세히 알아보려면 [그룹 비교를](../create-groups/compare-groups.md)참조하십시오.

    - Power Automate Office 스크립트를 사용하는 방법에 대해 자세히 알아보려면 [Power Automate Office 스크립트 실행을](/office/dev/scripts/develop/power-automate-integration)참조하십시오.

8. **저장** 을 선택합니다.

    스크립트 설정을 Office 변경하려면 최대 48시간이 걸릴 수 있습니다.

## <a name="next-steps"></a>다음 단계

Office 스크립트는 Power Automate 함께 작동하므로 사용자가 스크립트를 Office 사용하는 동안 조직의 데이터가 보호되도록 기존 DLP(데이터 손실 방지) 정책을 검토하는 것이 좋습니다. 자세한 내용은 [DLP(데이터 손실 방지) 정책을](/power-automate/prevent-data-loss)참조하십시오.

## <a name="related-content"></a>관련 콘텐츠

[Office 스크립트 기술 설명서(링크](/office/dev/scripts/) 페이지)\
[Excel Office 스크립트](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) 소개(기사)\
[웹(문서)에 대한 Excel Office 스크립트 공유\](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b)
[웹용 Excel Office 스크립트를 기록, 편집 및](/office/dev/scripts/tutorials/excel-tutorial) 만듭니다(문서)
