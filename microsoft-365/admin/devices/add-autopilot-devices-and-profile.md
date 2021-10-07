---
title: 단계별 가이드를 사용하여 AutoPilot 장치 및 프로필 추가
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.localizationpriority: medium
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: AutoPilot을 사용하여 Windows 사용할 수 있도록 비즈니스용 Windows 10 디바이스를 설정하는 방법을 배워야 합니다.
ms.openlocfilehash: 4b187d5e8f9acc8fb76e77770ec88790394dfbe3
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60165643"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>단계별 가이드를 사용하여 AutoPilot 장치 및 프로필 추가

AutoPilot을 Windows 사용하여 비즈니스용  새 Windows 10 디바이스를 설정할 수 있으므로 직원들에게 제공될 때 사용할 준비가 됩니다.
  
## <a name="device-requirements"></a>장치 요구 사항

장치는 다음 요구 사항을 충족해야 합니다.
  
- Windows 10 버전 1703 이상
    
- 2016년 1월 환경을 Windows 새 장치
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>설정 가이드를 사용하여 장치와 프로필 만들기

장치 그룹 또는 프로필을 아직 만들지 않은 경우 시작하는 가장 좋은 방법은 단계별 가이드를 사용하는 것입니다. 가이드를 [사용하지](create-and-edit-autopilot-devices.md) 않고 [](create-and-edit-autopilot-profiles.md) 디바이스를 추가하고 프로필을 할당할 수도 있습니다. 
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다.

2. 왼쪽 탐색 창에서 **장치** \> **AutoPilot 을 선택 합니다.**

    ![관리 센터에서 디바이스를 선택한 다음 AutoPilot을 선택하세요.](../../media/AutoPilot.png)
  
2. **AutoPilot 페이지에서** 시작 가이드를 **클릭하거나 탭합니다.**
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. 장치 **업로드 .csv** 파일 페이지에서 준비된 .CSV 위치로 이동한 후 다음  \> **열기 를 클릭합니다.** 파일에는 다음 세 개의 헤더가 있어야 합니다.
    
    - A 열: 장치 일련 번호
    
    - B 열: Windows 제품 ID
    
    - C 열: 하드웨어 해시
    
    하드웨어 공급업체에서 이 정보를 얻거나 [Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 스크립트를 사용하여 CSV 파일을 생성할 수 있습니다. 
    
    자세한 내용은 [장치 목록 CSV 파일](../misc/device-list.md)을 참조하세요. **장치 목록이 포함된 .csv 파일 업로드** 페이지에서 샘플 파일을 다운로드할 수도 있습니다. 
    
> [!NOTE]
> 이 스크립트는 WMI를 사용하여 고객이 Autopilot을 사용하여 디바이스를 등록하는 데 Windows 검색합니다. 디바이스를 등록할 필요는 아니며 출력 CSV에 NULL인 PKID가 완전히 괜찮기 때문에 결과 CSV 파일이 PKID(Windows 제품 ID) 값을 수집하지 않는 것은 일반적입니다. 일련 번호와 하드웨어 해시만 채워지기만 합니다.
    
4. 프로필 **할당 페이지에서** 기존 프로필을 선택하거나 새 프로필을 만들 수 있습니다. 아직 만들지 않은 경우 하나를 만들지 묻는 메시지가 표시될 것입니다. 
    
    프로필은 단일 장치 또는 장치 그룹에 적용할 수 있는 설정 모음입니다.
    
    기본 기능은 필수로 설정되며 자동으로 설정됩니다. 기본 기능은 다음과 같습니다.
    
    - 등록 Cortana, OneDrive 및 OEM 등록을 건너뜁.
    
    - 회사 브랜드의 로그인 환경을 만듭니다.
    
    - 커넥트 계정을 Azure Active Directory 등록하고 자동으로 등록하여 계정을 Microsoft 365 Business Premium.
    
    자세한 내용은 [AutoPilot 프로필 설정 정보를 참조하세요.](autopilot-profile-settings.md) 
    
5. 다른 설정은 **개인 정보 설정 건너뛰기** 및 **사용자가 로컬 관리자가 되는 것을 허용하지 않음** 입니다. 둘 다 기본적으로 **해제** 로 설정되어 있습니다. 
    
    **다음** 을 선택합니다.
    
6. **사용자가 만든(또는** 선택) 프로필이 장치 목록을 업로드하여 만든 디바이스 그룹에 적용될 것 같다고 나타냅니다. 설정은 장치 사용자가 다음에 로그인할 때 적용됩니다. **닫기** 를 선택합니다.

## <a name="related-content"></a>관련 콘텐츠

[AutoPilot 프로필 설정](autopilot-profile-settings.md) 정보(문서)\
[장치 및 앱 데이터 보호](../devices/choose-device-security.md) 옵션(문서)
