---
title: AutoPilot 프로필 만들기 및 편집
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
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
description: 'AutoPilot 프로필 만들기, 편집, 삭제 또는 제거 방법에 대해 알아봅니다. '
ms.openlocfilehash: 7987cafb3ea234d81be72c79aee8e584a3770875
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073493"
---
# <a name="create-and-edit-autopilot-profiles"></a>AutoPilot 프로필 만들기 및 편집

## <a name="create-a-profile"></a>프로필 만들기

프로필이 장치 또는 장치 그룹에 적용됩니다.
  
1. Microsoft 365 Business 관리 센터에서 **장치** \> **AutoPilot**을 선택 합니다.
  
2. **AutoPilot** 페이지에서 프로 파일 탭 **** \> **프로필 만들기**를 선택 합니다.
    
3. **프로필 만들기** 페이지에서 프로필을 식별하는 데 도움이 되는 프로필 이름(예: 마케팅)을 입력하고 원하는 설정을 켠 다음(자세한 내용은 [AutoPilot 프로필 설정 정보](autopilot-profile-settings.md) 참조) **저장**을 선택합니다.
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a>장치에 프로필 적용

프로필을 만든 후 장치 또는 장치 그룹에 적용할 수 있습니다. [단계별 가이드](add-autopilot-devices-and-profile.md)에서 기존 프로필을 선택하거나, 새 장치에 적용하거나, 장치 또는 장치 그룹의 기존 프로필을 바꿀 수 있습니다. 
  
1. **Windows 준비** 페이지에서 **장치** 탭을 선택합니다. 
    
2. Click the check-box next to a device name and in the **Device** panel, choose a profile from the **Assigned profile** drop-down \> **Save**.
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a>프로필 편집, 삭제 또는 제거

장치에 프로필을 할당했으면 사용자에게 장치를 이미 제공한 경우에도 프로필을 업데이트할 수 있습니다. 장치가 인터넷에 연결되면 설정 과정에서 최신 버전의 프로필을 다운로드합니다. 사용자가 장치를 초기 기본 설정으로 복원하면 장치가 프로필의 최신 업데이트를 다시 다운로드합니다. 
  
### <a name="edit-a-profile"></a>프로필 편집

1. **Windows 준비** 페이지에서 **프로필** 탭을 선택합니다. 
    
2. Click the check-box next to a device name and in the **Profile** panel update any of the available settings \> **Save**.
    
    사용자가 장치를 인터넷에 연결하기 전에 이 작업을 수행하면 프로필이 설정 프로세스에 적용됩니다.
    
### <a name="delete-a-profile"></a>프로필 삭제

1. **Windows 준비** 페이지에서 **프로필** 탭을 선택합니다. 
    
2. 장치 이름 옆의 확인란을 클릭하고 **프로필** 패널에서 **프로필 삭제** \> **저장**을 클릭합니다.
    
    프로필을 삭제하면 프로필이 할당된 장치 또는 장치 그룹에서 제거됩니다.
    
### <a name="remove-a-profile"></a>프로필 제거

1. **Windows 준비** 페이지에서 **장치** 탭을 선택합니다. 
    
2. Click the check-box next to a device name and in the **Device** panel, choose a **None** from the **Assigned profile** drop-down \> **Save**.
    
