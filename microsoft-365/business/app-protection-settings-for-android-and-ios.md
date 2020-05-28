---
title: Android 또는 iOS 장치에서 앱 보호 설정 설정하기
f1.keywords:
- NOCSH
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
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: 앱 관리 정책을 만들고, 편집 하 고, 삭제 하 고, Android 또는 iOS 장치에서 작업 파일을 보호 하는 방법을 알아봅니다.
ms.openlocfilehash: 01c50e6660d8d8640a2bff2794ee0ea8a69188c8
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401057"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a>Android 또는 iOS 장치에서 앱 보호 설정 설정하기

![를 가리키는 배너 https://aka.ms/aboutM365preview 입니다.](../media/m365admincenterchanging.png)

## <a name="create-an-app-management-policy"></a>앱 관리 정책 만들기

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다. 
    
2. 왼쪽 탐색 창에서 **장치** \> **정책** \> **추가**를 선택 합니다.
  
3. **정책 추가** 창에서 이 정책의 고유 이름을 입력합니다. 
    
4. **정책 유형에**서 만들려는 정책 집합에 따라 **Android 용 응용 프로그램 관리** 또는 **iOS 용 응용**프로그램 관리를 선택 합니다. 
    
5. **장치를 분실 하거나 도난당 한 경우 작업 파일 보호** 를 확장 하 고 **사용자가 모바일 장치에서 Office 파일에 액세스 하는 방법을 관리**합니다. 설정을 구성 하 여 원하는 방식으로 설정 합니다. **사용자가 모바일 장치에서 Office 파일에 액세스 하는 방법** 에 대 한 자세한 내용은 기본적으로 **해제** 되어 있지만 설정 **하 고 기본값** 을 그대로 사용 하는 것이 좋습니다. 자세한 내용은 [사용 가능한 설정을](#available-settings)참조 하십시오. 
    
    언제든지 **기본 설정 다시 설정** 링크를 사용하여 기본 설정으로 돌아갈 수 있습니다. 
    
    ![Screenshot of Create a policy with Application management for Android selected](../media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. Next decide **Who will get these settings?** 기본값인 **모든 사용자** 보안 그룹을 사용 하지 않으려는 경우 **변경을**선택 하 고 이러한 설정이 있는 보안 그룹을 \> **선택**합니다.
    
7. 마지막으로 **완료**를 선택하여 정책을 저장하고 장치를 할당합니다. 
    
## <a name="edit-an-app-management-policy"></a>앱 관리 정책 편집

1. **정책** 카드에서 **정책 편집**을 선택 합니다.
    
2. **정책 편집** 창에서 변경하려는 정책을 선택합니다. 
    
3. 정책에서 값을 변경하려는 각 설정 옆의 **편집**을 선택합니다. 값을 변경 하면 정책에 자동으로 저장 됩니다.
    
4. 작업이 완료 되 면 **정책 편집** 창을 닫습니다. 
    
## <a name="delete-an-app-management-policy"></a>앱 관리 정책 삭제

1. **정책 페이지에서** 정책을 선택 하 고 **삭제**를 클릭 합니다.
    
2. **정책 삭제** 창에서 **확인** 을 선택 하 여 선택한 정책 또는 정책을 삭제 합니다. 
    
## <a name="available-settings"></a>사용 가능한 설정

다음 표에서는 장치에서 작업 파일을 보호 하는 데 사용할 수 있는 설정 및 사용자가 모바일 장치에서 Office 파일에 액세스 하는 방법을 제어 하는 설정에 대해 자세히 설명 합니다.
  
 자세한 내용은 [Microsoft 365 Business Premium의 보호 기능을 Intune 설정에 매핑하는 방법을](map-protection-features-to-intune-settings.md)참조 하세요. 
  
### <a name="settings-that-protect-work-files"></a>업무 파일을 보호하는 설정

사용자가 장치를 분실하거나 도난당한 경우 다음과 같은 설정을 사용하여 업무 파일을 보호할 수 있습니다.
  
|||
|:-----|:-----|
|설정  <br/> |설명  <br/> |
|이 기간이 지난 후 비활성 장치에서 업무 파일 삭제  <br/> |여기에서 지정한 일 수 동안 장치가 사용 되지 않으면 장치에 저장 된 모든 작업 파일이 자동으로 삭제 됩니다.  <br/> |
|사용자가 모든 업무 파일을 비즈니스용 OneDrive에 저장하도록 강제 적용  <br/> |이 설정이 **켜져**있는 경우 작업 파일에 대해 사용할 수 있는 유일한 저장 위치는 비즈니스용 OneDrive입니다.  <br/> |
|업무 파일 암호화  <br/> |업무 파일이 암호화로 보호되도록 이 설정을 **켜짐**으로 둡니다. 장치를 분실 하거나 도난당 한 경우에도 아무도 회사 데이터를 읽을 수 없습니다.  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>사용자가 모바일 장치에서 Office 파일에 액세스하는 방법을 제어하는 설정

사용자가 Office 작업 파일을 액세스하는 방법을 관리할 때 다음과 같은 설정을 사용할 수 있습니다.
  
|||
|:-----|:-----|
|설정  <br/> |설명  <br/> |
|Office 앱 액세스에 PIN 또는 지문 필요  <br/> |이 설정이 사용자 **에** 게 제공 되는 경우 모바일 장치에서 Office 앱을 사용 하기 전에 다른 인증 형식 (사용자 이름 및 암호 추가)을 입력 해야 합니다.<br/> |
|PIN을 재설정할 로그인 실패 횟수  <br/> |권한 없는 사용자가 PIN을 임의로 추측하는 것을 방지하기 위해 사용자가 지정한 횟수만큼 잘못된 PIN이 입력되면 PIN을 재설정합니다.  <br/> |
|Office 앱이 이 시간 동안 유휴 상태인 경우 사용자 다시 로그인 필요  <br/> |이 설정은 사용자가 다시 로그인 하 라는 메시지가 표시 될 때까지 유휴 상태일 수 있는 기간을 결정 합니다.  <br/> |
|탈옥 또는 루팅된 장치에서의 작업 파일 액세스 거부  <br/> |기술을 잘 아는 사용자들은 장치를 탈옥 또는 루팅하여 사용할 수 있습니다. 즉, 사용자가 운영 체제를 수정할 수 있기 때문에 장치가 맬웨어에 노출될 확률이 높아집니다. 이 설정이 **켜기** 로 되어 있을 경우 이러한 장치는 차단됩니다.  <br/> |
|사용자가 Office 앱에서 개인 앱으로 콘텐츠를 복사 하도록 허용 하지 않음  <br/> |기본적으로 허용되는 설정이지만 이 설정이 **켜기**로 되어 있을 경우 사용자가 작업 파일의 정보를 개인 파일로 복사할 수 있습니다. 이 설정이 **끄기** 로 되어 있으면 사용자가 회사 계정의 정보를 개인 앱 또는 개인 계정으로 복사할 수 없습니다.  <br/> |
