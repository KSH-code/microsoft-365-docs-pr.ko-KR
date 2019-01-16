---
title: AutoPilot 장치 만들기 및 편집
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
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Microsoft 365 비즈니스에서 작업을 자동화할을 사용 하 여 장치를 업로드 하는 방법에 알아봅니다. 장치 또는 장치 그룹에는 프로필을 할당할 수 있습니다.
ms.openlocfilehash: cc1f81e9efd9b16e27b8abfbb0927d241535077e
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869968"
---
# <a name="create-and-edit-autopilot-devices"></a>AutoPilot 장치 만들기 및 편집

## <a name="upload-a-list-of-devices"></a>장치 목록 업로드

[단계별 가이드](add-autopilot-devices-and-profile.md) 를 사용하여 장치를 업로드할 수 있지만 **장치** 탭에서 업로드할 수도 있습니다. 
  
장치가 다음 요구 사항을 충족해야 합니다.
  
- Windows 10 버전 1703 이상
    
- Windows 첫 실행 경험을 완료하지 않은 새 장치
    
1. Microsoft 365 Business 관리 센터의 **장치 작업** 카드에서 **Autopilot으로 Windows 배포**를 선택합니다. 
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. **Windows 준비** 페이지에서 **장치** 탭 \> **장치 추가**를 선택합니다.
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. **추가 장치** 패널에서 준비한 [장치 목록 CSV 파일을](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) 이동 \> **저장** \> **닫기**합니다.
    
    하드웨어 공급업체로부터 이 정보를 얻거나 csv 파일을 생성하는 [Get-WindowsAutoPilotInfo PowerShell 스크립트](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)를 사용할 수 있습니다. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>장치 또는 장치 그룹에 프로필 할당

1. **Windows 준비** 페이지에서 **장치** 탭을 선택하고 하나 이상의 장치 옆에 있는 확인란을 선택합니다. 
    
2. **장치** 패널의 **할당된 프로필** 드롭다운에서 프로필을 선택합니다. 
    
    아직 프로필이 없는 경우 지침은 [AutoPilot 프로필 만들기 및 편집](create-and-edit-autopilot-profiles.md)을 참조하세요. 
    
