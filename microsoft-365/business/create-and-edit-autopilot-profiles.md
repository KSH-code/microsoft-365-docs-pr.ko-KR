---
title: AutoPilot 프로필 만들기 및 편집
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: '만들기, 편집, 삭제 또는 작업을 자동화할 프로필을 제거 하는 방법을 알아봅니다. '
ms.openlocfilehash: 4658a27e5f2c64a52f8a7d08b3fc13df5e239dc3
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26870023"
---
# <a name="create-and-edit-autopilot-profiles"></a>AutoPilot 프로필 만들기 및 편집

## <a name="create-a-profile"></a>프로필 만들기

프로필이 장치 또는 장치 그룹에 적용됩니다.
  
1. Microsoft 365 Business 관리 센터의 **장치 작업** 카드에서 **Autopilot으로 Windows 배포**를 선택합니다. 
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. **Windows 준비** 페이지에서 **프로필** 탭 \> **프로필 만들기**를 선택합니다.
    
3. **프로필 만들기** 페이지에서 프로필을 식별하는 데 도움이 되는 프로필 이름(예: 마케팅)을 입력하고 원하는 설정을 켠 다음(자세한 내용은 [AutoPilot 프로필 설정 정보](autopilot-profile-settings.md) 참조) **저장**을 선택합니다.
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a>장치에 프로필 적용

프로필을 만든 후 장치 또는 장치 그룹에 적용할 수 있습니다. [단계별 가이드](add-autopilot-devices-and-profile.md)에서 기존 프로필을 선택하거나, 새 장치에 적용하거나, 장치 또는 장치 그룹의 기존 프로필을 바꿀 수 있습니다. 
  
1. **Windows 준비** 페이지에서 **장치** 탭을 선택합니다. 
    
2. 확인란을 클릭-장치 이름 옆에 있는 및 **장치** 패널에서, **할당 된 프로필** 드롭다운 메뉴에서 프로필을 선택 \> **저장**합니다.
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a>프로필 편집, 삭제 또는 제거

장치에 프로필을 할당했으면 사용자에게 장치를 이미 제공한 경우에도 프로필을 업데이트할 수 있습니다. 장치가 인터넷에 연결되면 설정 과정에서 최신 버전의 프로필을 다운로드합니다. 사용자가 장치를 초기 기본 설정으로 복원하면 장치가 프로필의 최신 업데이트를 다시 다운로드합니다. 
  
### <a name="edit-a-profile"></a>프로필 편집

1. **Windows 준비** 페이지에서 **프로필** 탭을 선택합니다. 
    
2. 장치 이름 옆에 있는 확인란을 클릭 하 고 **프로필** 에서 패널 사용 가능한 설정을 업데이트 \> **저장**합니다.
    
    사용자가 장치를 인터넷에 연결하기 전에 이 작업을 수행하면 프로필이 설정 프로세스에 적용됩니다.
    
### <a name="delete-a-profile"></a>프로필 삭제

1. **Windows 준비** 페이지에서 **프로필** 탭을 선택합니다. 
    
2. 장치 이름 옆의 확인란을 클릭하고 **프로필** 패널에서 **프로필 삭제** \> **저장**을 클릭합니다.
    
    프로필을 삭제하면 프로필이 할당된 장치 또는 장치 그룹에서 제거됩니다.
    
### <a name="remove-a-profile"></a>프로필 제거

1. **Windows 준비** 페이지에서 **장치** 탭을 선택합니다. 
    
2. 확인란을 클릭-장치 이름 옆에 있는 및 **장치** 패널에서, **담당자 프로필** 드롭다운 메뉴에서 **없음을** 선택 \> **저장**합니다.
    
