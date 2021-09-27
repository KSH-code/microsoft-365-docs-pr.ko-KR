---
title: Android 또는 iOS 장치에서 앱 보호 설정 설정하기
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: 앱 관리 정책을 생성, 편집 또는 삭제하고 Android 또는 iOS 디바이스에서 작업 파일을 보호하는 방법을 학습합니다.
ms.openlocfilehash: f11782a4a2671f1a5e5dc467f181421817634880
ms.sourcegitcommit: 34259ec9b6cccc8f6e29808dbe4796d9f72b651b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/27/2021
ms.locfileid: "59933282"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a>Android 또는 iOS 장치에서 앱 보호 설정 설정하기

이 문서는 이 문서에 Microsoft 365 Business Premium.

## <a name="create-an-app-management-policy"></a>앱 관리 정책 만들기

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다. 
    
2. 왼쪽 nav에서 장치  정책 \> **추가 를** \> **선택 합니다.**
  
3. **정책 추가** 창에서 이 정책의 고유 이름을 입력합니다. 
    
4. 정책 **유형에서** 만들 정책 집합에 따라 **Android용** 응용 프로그램 관리 또는 **iOS용 응용** 프로그램 관리를 선택하십시오. 
    
5. 장치를 **분실하거나** 도난당한 경우 작업 파일 보호를 확장하고 사용자가 모바일 장치에서 Office 파일에 액세스하는 방법 **관리를 확장합니다.** 원하는 설정을 구성합니다. **사용자가 모바일** Office 파일에 액세스하는 방법을  관리 기본적으로 해제되어 있지만, 켜고 기본값을 수락하는 것이 좋습니다.  자세한 내용은 사용 가능한 설정을 [참조하세요.](#available-settings) 
    
    언제든지 **기본 설정 다시 설정** 링크를 사용하여 기본 설정으로 돌아갈 수 있습니다. 
    
    ![Screenshot of Create a policy with Application management for Android selected.](../../media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. Next decide **Who will get these settings?** 기본 모든 사용자 보안 그룹을  사용하지 않는 경우 변경 을 선택하고 이러한 설정을 사용하는 보안 그룹을 \> **선택합니다.**
    
7. 마지막으로 **완료** 를 선택하여 정책을 저장하고 장치를 할당합니다. 
    
## <a name="edit-an-app-management-policy"></a>앱 관리 정책 편집

1. 정책 **카드에서** 정책 **편집 을 선택 합니다.**
    
2. **정책 편집** 창에서 변경하려는 정책을 선택합니다. 
    
3. 정책에서 값을 변경하려는 각 설정 옆의 **편집** 을 선택합니다. 값을 변경하면 정책에 자동으로 저장됩니다.
    
4. 완료되면 정책 편집 **창을 닫습니다.** 
    
## <a name="delete-an-app-management-policy"></a>앱 관리 정책 삭제

1. 정책 **페이지에서** 정책을 선택한 다음 삭제 **를 선택합니다.**
    
2. 정책 **삭제 창에서** 확인을 선택하고 선택한 정책 또는 정책을 삭제합니다.  
    
## <a name="available-settings"></a>사용 가능한 설정

다음 표에서는 장치에서 작업 파일을 보호하는 데 사용할 수 있는 설정과 사용자가 모바일 장치에서 Office 파일에 액세스하는 방법을 제어하는 설정에 대한 자세한 정보를 제공합니다.
  
 자세한 내용은 [Intune 설정에](map-protection-features-to-intune-settings.md)매핑되는 Microsoft 365 Business Premium 방법을 참조하세요. 
  
### <a name="settings-that-protect-work-files"></a>업무 파일을 보호하는 설정

사용자가 장치를 분실하거나 도난당한 경우 다음과 같은 설정을 사용하여 업무 파일을 보호할 수 있습니다.


|설정  <br/> |설명  <br/> |
|:-----|:-----|
|이 기간이 지난 후 비활성 장치에서 업무 파일 삭제  <br/> |여기서 지정한 일 수 동안 디바이스를 사용하지 않으면 장치에 저장된 모든 작업 파일이 자동으로 삭제됩니다.  <br/> |
|사용자가 모든 업무 파일을 비즈니스용 OneDrive에 저장하도록 강제 적용  <br/> |이 설정이 **으로** 설정되어 있는 경우 작업 파일에 사용할 수 있는 유일한 저장 위치는 비즈니스용 OneDrive.  <br/> |
|업무 파일 암호화  <br/> |업무 파일이 암호화로 보호되도록 이 설정을 **켜짐** 으로 둡니다. 장치를 분실하거나 도난당한 경우에도 누구도 회사 데이터를 읽을 수 없습니다.  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>사용자가 모바일 장치에서 Office 파일에 액세스하는 방법을 제어하는 설정

사용자가 Office 작업 파일을 액세스하는 방법을 관리할 때 다음과 같은 설정을 사용할 수 있습니다.


|설정  <br/> |설명  <br/> |
|:-----|:-----|
|Office 앱 액세스에 PIN 또는 지문 필요  <br/> |이 설정이 **On인** 경우 사용자는 자신의 사용자 이름 및 암호와 함께 다른 형태의 인증을 제공해야 모바일 장치에서 Office 사용할 수 있습니다.<br/> |
|PIN을 재설정할 로그인 실패 횟수  <br/> |권한 없는 사용자가 PIN을 임의로 추측하는 것을 방지하기 위해 사용자가 지정한 횟수만큼 잘못된 PIN이 입력되면 PIN을 재설정합니다.  <br/> |
|Office 앱이 이 시간 동안 유휴 상태인 경우 사용자 다시 로그인 필요  <br/> |이 설정은 다시 로그인하라는 메시지가 표시되기 전에 사용자가 유휴일 수 있는 기간을 결정하는 설정입니다.  <br/> |
|탈옥 또는 루팅된 장치에서의 작업 파일 액세스 거부  <br/> |기술을 잘 아는 사용자들은 장치를 탈옥 또는 루팅하여 사용할 수 있습니다. 즉, 사용자가 운영 체제를 수정할 수 있기 때문에 장치가 맬웨어에 노출될 확률이 높아집니다. 이 설정이 **켜기** 로 되어 있을 경우 이러한 장치는 차단됩니다.  <br/> |
|사용자가 앱의 콘텐츠를 개인 앱으로 Office 허용하지 않습니다.  <br/> |기본적으로 허용되는 설정이지만 이 설정이 **켜기** 로 되어 있을 경우 사용자가 작업 파일의 정보를 개인 파일로 복사할 수 있습니다. 이 설정이 **끄기** 로 되어 있으면 사용자가 회사 계정의 정보를 개인 앱 또는 개인 계정으로 복사할 수 없습니다.  <br/> |
