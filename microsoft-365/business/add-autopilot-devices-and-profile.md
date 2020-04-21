---
title: 단계별 가이드를 사용하여 AutoPilot 장치 및 프로필 추가
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-subscription-management
- M365-identity-device-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Windows AutoPilot를 사용 하 여 비즈니스에 대 한 새 Windows 10 장치를 설정 하 여 직원 들이 사용할 수 있도록 준비 하는 방법을 알아봅니다.
ms.openlocfilehash: 98a2bfc721ce86c81ebd89e8f41603e619b31546
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627497"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>단계별 가이드를 사용하여 AutoPilot 장치 및 프로필 추가

Windows AutoPilot를 사용 하 여 비즈니스에 대 한 **새** windows 10 장치를 설정 하 여 직원 들에 게 제공할 때 사용할 수 있도록 준비 합니다.
  
## <a name="device-requirements"></a>장치 요구 사항

장치는 다음 요구 사항을 충족 해야 합니다.
  
- Windows 10, 버전 1703 이상
    
- Windows 기본 경험을 거치지 않은 새로운 장치
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>설정 가이드를 사용하여 장치와 프로필 만들기

[![관리 센터가 변경되고 있음을 알리는 레이블이며 aka.ms/aboutM365preview에서 자세한 내용을 확인할 수 있습니다.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

아직 장치 그룹 또는 프로필을 만들지 않은 경우에는 단계별 가이드를 사용 하 여 시작 하는 것이 가장 좋습니다. 가이드를 사용 하지 않고 [장치를 추가](create-and-edit-autopilot-devices.md) 하 고 [프로필을 할당할](create-and-edit-autopilot-profiles.md) 수도 있습니다. 
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다.

2. 왼쪽 탐색 창에서 **장치** \> **AutoPilot**을 선택 합니다.

    ![관리 센터에서 장치, AutoPilot을 차례로 선택 합니다.](../media/AutoPilot.png)
  
2. **AutoPilot** 페이지에서 **시작 가이드**를 클릭 하거나 탭 합니다.
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. **장치 목록이 포함 된 .csv 파일 업로드** 페이지에서 준비 된 위치로 이동 합니다. CSV 파일을 선택한 후 **다음**을 **엽니다** \> . 파일에는 다음과 같은 세 가지 헤더가 있어야 합니다.
    
    - A 열: 장치 일련 번호
    
    - B 열: Windows 제품 ID
    
    - C 열: 하드웨어 해시
    
    하드웨어 공급 업체에서이 정보를 가져오거나 [Get-windowsautopilotinfo PowerShell 스크립트](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 를 사용 하 여 CSV 파일을 생성할 수 있습니다. 
    
    자세한 내용은 [장치 목록 CSV 파일](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e)을 참조하세요. **장치 목록이 포함된 .csv 파일 업로드** 페이지에서 샘플 파일을 다운로드할 수도 있습니다. 
    
4. **프로필 할당** 페이지에서 기존 프로필을 선택 하거나 새로 만들 수 있습니다. 아직 없으면 만들 것인지 묻는 메시지가 표시 됩니다. 
    
    프로필은 단일 장치 또는 장치 그룹에 적용할 수 있는 설정 모음입니다.
    
    기본 기능은 필수 이며 자동으로 설정 됩니다. 기본 기능은 다음과 같습니다.
    
    - Cortana, OneDrive 및 OEM 등록을 건너뜁니다.
    
    - 회사 브랜드의 로그인 환경을 만듭니다.
    
    - 장치를 Azure Active Directory 계정에 연결 하 고 Microsoft 365 Business Premium에서 관리할 수 있도록 자동으로 등록 합니다.
    
    자세한 내용은 [About AutoPilot Profile settings](autopilot-profile-settings.md)를 참조 하십시오. 
    
5. 다른 설정은 **개인 정보 설정 건너뛰기** 및 **사용자가 로컬 관리자가 되는 것을 허용하지 않음**입니다. 둘 다 기본적으로 **해제**로 설정되어 있습니다. 
    
    **다음**을 선택합니다.
    
6. **사용자** 가 만들거나 선택한 프로필이 장치 목록을 업로드 하 여 만든 장치 그룹에 적용 됨을 나타냅니다. 설정은 장치 사용자가 다음에 로그인 할 때 적용 됩니다. **닫기**를 선택합니다.
    
