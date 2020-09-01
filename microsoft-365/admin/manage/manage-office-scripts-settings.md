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
description: 조직의 사용자에 대 한 Office 스크립트 설정을 관리 하는 방법을 알아봅니다.
ms.openlocfilehash: 44e2a5c0e0577db344fdbb00a110674df3e71bdc
ms.sourcegitcommit: 04f196528a7a91b404478553433af3fa94d7eee7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2020
ms.locfileid: "47317496"
---
# <a name="manage-office-scripts-settings"></a>Office 스크립트 설정 관리

Office 스크립트를 사용 하면 사용자가 웹에서 Excel에서 스크립트를 기록, 편집 및 실행 하 여 작업을 자동화할 수 있습니다. Office 스크립트는 전원 자동화와 함께 작동 하며, 사용자는 Excel Online (Business) 커넥터를 사용 하 여 통합 문서에서 스크립트를 실행 합니다. Microsoft 365 관리자는 Microsoft 365 관리 센터에서 Office 스크립트 설정을 관리할 수 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

- Office 스크립트 설정을 관리 하려면 전역 관리자 여야 합니다. 자세한 내용은 [관리 역할 정보](../add-users/about-admin-roles.md)를 참조 하세요.

- 조직의 사용자에 게 다음 계획 중 하 나와 같은 Office 데스크톱 앱에 대 한 액세스를 포함 하는 Microsoft 365 또는 Office 365 상업용 또는 .EDU 계획에 대 한 유효한 라이선스가 있는지 확인 합니다.

    - Microsoft 365 Business Standard
    - 비즈니스용 Microsoft 365 앱
    - 엔터프라이즈용 Microsoft 365 앱
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>Office 스크립트 사용 가능 여부 관리 및 스크립트 공유

1. Microsoft 365 관리 센터에서 **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> 탭으로 이동 합니다.

2. **Office 스크립트**를 선택 합니다.

3. Office 스크립트는 기본적으로 설정 되어 있으며 조직의 모든 사용자가 기능에 액세스 하 고 스크립트를 공유할 수 있습니다. 조직에 대해 Office 스크립트를 해제 하려면 **사용자가 웹에서 Excel에서 작업 자동화** 확인란의 선택을 취소 합니다.

4. 이전에 조직에 대해 Office 스크립트를 해제 한 경우 다시 설정 하려면 **사용자가 웹에서 Excel에서 작업을 자동화 하도록 허용**을 선택 하 고 다음 기능에 액세스 하 여 사용할 수 있는 사용자를 지정 합니다.

    - 조직의 모든 사용자가 Office 스크립트에 액세스 하 고 사용할 수 있도록 허용 하려면 **모든 사람** (기본값)을 선택 된 채로 두세요. 

    - 특정 그룹의 구성원만 Office 스크립트에 액세스 하 고 사용할 수 있도록 하려면 **특정 그룹**을 선택한 다음 그룹의 이름 또는 전자 메일 별칭을 입력 하 여 허용 목록에 추가 합니다. 허용 목록에는 그룹을 하나만 추가할 수 있으며 다음 형식 중 하나 여야 합니다.
        - Microsoft 365 그룹
        - 메일 그룹
        - 보안 그룹
        - 메일 사용 가능 보안 그룹
    
        다양 한 유형의 그룹에 대 한 자세한 내용은 [Compare groups](../create-groups/compare-groups.md)를 참조 하십시오.

5. Office 스크립트에 대 한 액세스 권한이 있는 사용자가 자신의 스크립트를 조직의 다른 사용자와 공유할 수 있도록 허용 하려면 **Office 스크립트 액세스 권한이 있는 사용자에 게 조직의 다른 사용자와 스크립트를 공유**하도록 합니다 .를 선택 합니다. 조직 외부에서 스크립트를 공유 하는 것은 허용 되지 않습니다.
 
    > [!NOTE]
    > 나중에 조직의 스크립트 공유 기능을 해제 하는 경우 사용자는 이전에 공유 된 스크립트를 계속 실행할 수 있습니다.
 
6. Office 스크립트에 대 한 액세스 권한이 있는 사용자가 스크립트를 공유할 수 있도록 지정 합니다.
    
    - Office 스크립트에 액세스 하는 모든 사용자가 자신의 스크립트를 공유할 수 있도록 하려면 모든 **사람** (기본값)을 선택 된 상태로 유지 합니다.

    - Office 스크립트에 대 한 액세스 권한이 있는 특정 그룹의 구성원만 스크립트를 공유할 수 있도록 하려면 **특정 그룹**을 선택한 다음 그룹의 이름이 나 전자 메일 별칭을 입력 하 여 허용 목록에 추가 합니다. 허용 목록에는 그룹을 하나만 추가할 수 있으며 다음 형식 중 하나 여야 합니다.
        - Microsoft 365 그룹
        - 메일 그룹
        - 보안 그룹
        - 메일 사용 가능 보안 그룹
    
        다양 한 유형의 그룹에 대 한 자세한 내용은 [Compare groups](../create-groups/compare-groups.md)를 참조 하십시오.

7. **저장**을 선택합니다.

    Office 스크립트 설정 변경 사항을 적용 하려면 최대 48 시간이 걸릴 수 있습니다.

## <a name="next-steps"></a>다음 단계

Office 스크립트는 전원 자동화와 함께 작동 하기 때문에 사용자가 Office 스크립트를 사용 하는 동안 기존 DLP (데이터 손실 방지) 정책을 검토 하 여 조직의 데이터가 보호 된 상태로 유지 되도록 하는 것이 좋습니다. 자세한 내용은 [DLP (데이터 손실 방지) 정책을](/power-automate/prevent-data-loss)참조 하세요.

## <a name="related-content"></a>관련 콘텐츠

[Office 스크립트 기술 설명서](/office/dev/scripts/) (링크 페이지) \
[Excel의 Office 스크립트 소개](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (문서) \
[Excel에서 웹에 대 한 Office 스크립트 공유](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (문서) \
[웹에서 Excel의 Office 스크립트 기록, 편집 및 만들기](/office/dev/scripts/tutorials/excel-tutorial) (문서)