---
title: 단계별 가이드를 사용하여 AutoPilot 장치 및 프로필 추가
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: 비즈니스에 대 한 새 Windows 10 장치를 설정 하려면 Windows 작업을 자동화할을 사용 하는 방법에 알아봅니다.
ms.openlocfilehash: 56225424125e9eed9f46867837c564aa5d1c4adc
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869717"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>단계별 가이드를 사용하여 AutoPilot 장치 및 프로필 추가

Windows AutoPilot을 사용하여 비즈니스용 새 Windows 10 장치를 설정할 수 있으며 직원에게 제공하는 즉시 생산성 있게 사용할 준비가 됩니다.
  
## <a name="device-requirements"></a>장치 요구 사항

장치가 다음 요구 사항을 충족해야 합니다.
  
- Windows 10 버전 1703 이상
    
- Windows 첫 실행 경험을 완료하지 않은 새 장치
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>설정 가이드를 사용하여 장치와 프로필 만들기

장치 그룹 또는 프로필을 아직 만들지 않은 경우 시작하는 가장 좋은 방법은 단계별 가이드를 사용하는 것이지만, 가이드를 사용하지 않고 [장치를 추가](create-and-edit-autopilot-devices.md)하고 [프로필을 할당](create-and-edit-autopilot-profiles.md)할 수도 있습니다. 
  
1. Microsoft 365 Business 관리 센터에서 **장치 작업** 카드를 찾은 다음 **Autopilot으로 Windows 배포**를 선택합니다.
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. **Windows 준비** 페이지에서 **시작 가이드**를 클릭하거나 탭합니다.
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. **장치 목록이 포함된 .csv 파일 업로드** 페이지에서 준비된 .CSV 파일이 있는 위치로 이동한 후 **열기** \> **다음**을 클릭합니다. 파일에 다음 3개의 머리글이 있어야 합니다.
    
  - A 열: 장치 일련 번호
    
  - B 열: Windows 제품 ID
    
  - C 열: 하드웨어 해시
    
    하드웨어 공급업체로부터 이 정보를 얻거나 CSV 파일을 생성하는 [Get-WindowsAutoPilotInfo PowerShell 스크립트](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)를 사용할 수 있습니다. 
    
    자세한 내용은 [장치 목록 CSV 파일](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e)을 참조하세요. **장치 목록이 포함된 .csv 파일 업로드** 페이지에서 샘플 파일을 다운로드할 수도 있습니다. 
    
4. **프로필 할당** 페이지에서 기존 프로필을 선택하거나 새 프로필을 만들 수 있습니다. 아직 프로필이 없는 경우 새 프로필을 만들라는 메시지가 표시됩니다. 
    
    프로필은 단일 장치 또는 장치 그룹에 적용할 수 있는 설정 모음입니다.
    
    기본 기능은 필수이며 자동으로 설정됩니다. 기본 기능은 다음과 같습니다.
    
  - Cortana, OneDrive 및 OEM 등록은 건너뜁니다.
    
  - 회사 브랜드의 로그인 환경을 만듭니다.
    
  - 장치가 Azure Active Directory 계정에 연결되고 Microsoft 365 Business에서 관리하도록 자동으로 등록됩니다.
    
    자세한 내용은
    
    [AutoPilot 프로필 설정 정보](autopilot-profile-settings.md) 를 참조하세요. 
    
5. 다른 설정은 **개인 정보 설정 건너뛰기** 및 **사용자가 로컬 관리자가 되는 것을 허용하지 않음**입니다. 둘 다 기본적으로 **해제**로 설정되어 있습니다. 
    
    **다음**을 선택합니다.
    
6. **모두 마쳤습니다** 페이지는 만들었거나 선택한 프로필이 장치 목록을 업로드하여 만든 장치 그룹에 적용됨을 나타냅니다. 이러한 설정은 장치 사용자가 다음에 로그인할 때 적용됩니다. **닫기**를 선택합니다.
    