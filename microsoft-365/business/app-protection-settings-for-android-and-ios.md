---
title: Android 또는 iOS 장치에서 앱 보호 설정 설정하기
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
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: 만들기, 편집 또는 삭제 한 응용 프로그램 관리 정책 및 Android 또는 iOS 장치에서 작업 파일을 보호 하는 방법에 알아봅니다.
ms.openlocfilehash: ed03227496120369b94bf2396974eebfd7798678
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26870289"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a>Android 또는 iOS 장치에서 앱 보호 설정 설정하기

## <a name="create-an-app-management-policy"></a>앱 관리 정책 만들기

1. 전역 관리자 자격 증명을 사용하여 [Microsoft 365 Business](https://portal.office.com)에 로그인합니다. 
    
2. 관리 센터의 **장치 정책** 카드에서 **정책 추가**를 선택합니다.
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. **정책 추가** 창에서 이 정책의 고유 이름을 입력합니다. 
    
4. **정책 유형**에서 만들려는 정책의 집합에 따라 **Android용 응용 프로그램 관리** 또는 **iOS용 응용 프로그램 관리**를 선택합니다. 
    
5. **장치는 분실 또는 도난당 한 경우 암호로 보호 작업 파일** 및 **사용자가 모바일 장치에서 Office 파일을 액세스 하는 방식을 관리할** 확장 \> 하려는 방식 설정을 구성 합니다. 기본적으로 **해제** 되어 **사용자가 모바일 장치에서 Office 파일을 액세스 하는 방식을 관리** 하지만 **에** 설정 하 고 기본값을 적용 하는 것이 좋습니다. 자세한 내용은 [사용할 수 있는 설정](app-protection-settings-for-android-and-ios.md#bkmk_availablesettings) 을 참조 하십시오. 
    
    언제든지 **기본 설정 다시 설정** 링크를 사용하여 기본 설정으로 돌아갈 수 있습니다. 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. 다음으로 **이러한 설정을 적용할 대상은 누구입니까?** 를 설정하세요. **모든 사용자** 기본 보안 그룹을 사용하지 않으려는 경우 **변경**을 선택하고 이 설정을 적용할 보안 그룹 \> **선택**을 선택합니다.
    
7. 마지막으로 **완료**를 선택하여 정책을 저장하고 장치를 할당합니다. 
    
## <a name="edit-an-app-management-policy"></a>앱 관리 정책 편집

1. **정책** 카드 **정책 편집**을 선택 합니다.
    
2. **정책 편집** 창에서 변경하려는 정책을 선택합니다. 
    
3. 정책에서 값을 변경하려는 각 설정 옆의 **편집**을 선택합니다. 변경한 값은 정책에 자동으로 저장됩니다. 
    
4. 편집을 완료하고 **정책 편집** 창을 닫습니다. 
    
## <a name="delete-an-app-management-policy"></a>앱 관리 정책 삭제

1. **정책** 카드에서 **정책 삭제**를 선택합니다.
    
2. **정책 삭제** 창에서 삭제할 정책 \> **선택**, **확인**을 차례로 선택하여 정책 또는 선택한 정책을 삭제합니다. 
    
## <a name="available-settings"></a>사용 가능한 설정

다음 표에서는 장치에서 작업 파일을 보호하기 위해 사용 가능한 설정 및 사용자가 모바일 장치에서 Office 파일에 액세스하는 방법을 제어하는 설정에 대한 자세한 정보를 제공합니다.
  
 자세한 내용은 [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md)(Microsoft 365 Business의 보호 기능을 Intune 설정에 매핑하는 방법)를 참조하세요. 
  
### <a name="settings-that-protect-work-files"></a>작업 파일을 보호하는 설정

사용자가 장치를 분실하거나 도난당한 경우 다음과 같은 설정을 사용하여 작업 파일을 보호할 수 있습니다.
  
|||
|:-----|:-----|
|설정  <br/> |설명  <br/> |
|이 기간이 지난 후 비활성 장치에서 작업 파일 삭제  <br/> |여기에 지정한 기간만큼 장치가 사용되지 않는 경우 장치에 저장된 모든 작업 파일이 자동으로 삭제됩니다.  <br/> |
|사용자가 모든 작업 파일을 비즈니스용 OneDrive에 저장하도록 강제 적용  <br/> |이 설정이 **켜기**로 되어 있으면 작업 파일은 오직 비즈니스용 OneDrive에만 저장할 수 있습니다.  <br/> |
|작업 파일 암호화  <br/> |작업 파일이 암호화로 보호되도록 이 설정을 **켜기**로 둡니다. 장치를 분실하거나 도난당하더라도 다른 사람이 회사 데이터를 읽을 수 없게 됩니다.  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>사용자가 모바일 장치에서 Office 파일에 액세스하는 방법을 제어하는 설정

사용자가 Office 작업 파일을 액세스하는 방법을 관리할 때 다음과 같은 설정을 사용할 수 있습니다.
  
|||
|:-----|:-----|
|설정  <br/> |설명  <br/> |
|Office 앱 액세스에 PIN 또는 지문 필요  <br/> |이 설정이 **켜기**로 되어 있으면 사용자는 사용자 이름 및 암호 외에도 또 다른 형태의 인증을 제공해야 모바일 장치에서 Office 앱을 사용할 수 있습니다.  <br/> |
|PIN을 재설정할 로그인 실패 횟수  <br/> |권한 없는 사용자가 PIN을 임의로 추측하는 것을 방지하기 위해 사용자가 지정한 횟수만큼 잘못된 PIN이 입력되면 PIN을 재설정합니다.  <br/> |
|Office 앱이 이 시간 동안 유휴 상태인 경우 사용자 다시 로그인 필요  <br/> |사용자가 얼마 동안 유휴 상태이면 다시 로그인해야 하는지 지정합니다.  <br/> |
|탈옥 또는 루팅된 장치에서의 작업 파일 액세스 거부  <br/> |기술을 잘 아는 사용자들은 장치를 탈옥 또는 루팅하여 사용할 수 있습니다. 즉, 사용자가 운영 체제를 수정할 수 있기 때문에 장치가 맬웨어에 노출될 확률이 높아집니다. 이 설정이 **켜기** 로 되어 있을 경우 이러한 장치는 차단됩니다.  <br/> |
|사용자가 Office 앱의 콘텐츠를 개인 앱으로 복사할 수 있도록 허용  <br/> |기본적으로 허용지 않습니다는 있지만 설정에 **** 있으면 사용자 수 복사 정보 작업 파일에 개인 파일을 합니다. 이 설정이 이면 **해제**하는 경우 사용자 개인 응용 프로그램 또는 개인 계정으로 작업 계정에서 정보를 복사할 수 없습니다.<br/> |
   

  

