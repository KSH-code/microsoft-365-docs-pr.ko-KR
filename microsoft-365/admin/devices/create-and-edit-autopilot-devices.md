---
title: AutoPilot 장치 만들기 및 편집
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: 장치에서 AutoPilot을 사용하여 디바이스를 업로드하는 방법을 Microsoft 365 Business Premium. 장치 또는 장치 그룹에 프로필을 할당할 수 있습니다.
ms.openlocfilehash: 96034ca50da114adca60169ae29da5948793b498
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60165559"
---
# <a name="create-and-edit-autopilot-devices"></a>AutoPilot 장치 만들기 및 편집

## <a name="upload-a-list-of-devices"></a>장치 목록 업로드

단계별 가이드를 사용하여 디바이스를 업로드할 수 있지만 장치 탭에서 디바이스를 업로드할 **수도** 있습니다. [](add-autopilot-devices-and-profile.md) 
  
장치는 다음 요구 사항을 충족해야 합니다.
  
- Windows 10 버전 1703 이상
    
- 2016년 1월 환경을 Windows 새 장치

1. In the Microsoft 365 관리 센터, choose **Devices** \> **AutoPilot**.
  
2. **AutoPilot 페이지에서** 장치 탭 **장치** \> **추가 를 선택합니다.**
    
    ![In the Devices tab, choose Add devices.](../../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. 장치 **추가 패널에서** 저장 닫기 를 준비한 장치 목록 [CSV](../misc/device-list.md) \> **파일을** \> **검색합니다.**
    
    하드웨어 공급업체에서 이 정보를 얻거나 [Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 스크립트를 사용하여 CSV 파일을 생성할 수 있습니다. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>장치 또는 장치 그룹에 프로필 할당

1. 장치 **Windows** 페이지에서 장치 탭을  선택하고 하나 이상의 장치 옆에 있는 확인란을 선택합니다. 
    
2. **장치** 패널의 **할당된 프로필** 드롭다운에서 프로필을 선택합니다. 
    
    아직 프로필이 없는 경우 지침은 [AutoPilot 프로필 만들기 및 편집](create-and-edit-autopilot-profiles.md)을 참조하세요. 
