---
title: Android 또는 iOS 장치에서 앱 보호 설정 유효성 검사
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: Android 또는 iOS 장치에서 Microsoft 365 Business Premium 앱 보호 설정의 유효성을 검사하는 방법을 확인합니다.
ms.openlocfilehash: aaad8d11cb983973b6aaa2efe838de21712ef50a
ms.sourcegitcommit: 34259ec9b6cccc8f6e29808dbe4796d9f72b651b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/27/2021
ms.locfileid: "59933402"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a>Android 또는 iOS 장치에서 앱 보호 설정 유효성 검사

다음 섹션의 지침에 따라 Android 또는 iOS 장치에서 앱 보호 설정의 유효성을 검사합니다.
  
## <a name="android"></a>Android
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>사용자 장치에서 앱 보호 설정이 작동하고 있는지 확인

[Android 장치에 대한 앱 구성을 설정](app-protection-settings-for-android-and-ios.md) 한 후 앱을 보호하려면 다음 단계를 따라 선택한 설정이 작동하는지 확인하세요. 
  
먼저 정책이 유효성을 검사할 앱에 적용해야 합니다.
  
1. Microsoft 365 Business Premium [관리 센터에서](https://admin.microsoft.com)정책 편집  \> **정책으로 이동하세요.**
    
2. 설치 시 만든 설정에 **대해 Android용** 응용 프로그램 정책 또는 만든 다른 정책을 선택하고 응용 프로그램에 Outlook 확인합니다. 
    
    ![Shows all the apps for which this policy protects files.](../../media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a>Office 앱 액세스에 PIN 또는 지문 필요 유효성 검사

**정책 편집** 창에서 **Office 문서 액세스 제어** 옆의 **편집** 을 선택하고 **사용자가 모바일 장치에서 Office 파일에 액세스하는 방법 관리** 를 확장한 다음 **Office 앱 액세스에 PIN 또는 지문 필요** 가 **켜기** 로 설정되어 있는지 확인합니다.
  
![앱에 액세스하려면 PIN 또는 지문 필요 Office 설정되어 있는지 확인 합니다.](../../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. 사용자의 Android 장치에서 Outlook 열고 사용자의 Microsoft 365 Business Premium 자격 증명으로 로그인합니다.
    
2. PIN을 입력하거나 지문을 사용하라는 메시지가 표시될 수도 있습니다.
    
    ![Enter a PIN on your Android device to access Office apps.](../../media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>시도가 몇 번 실패한 후 PIN 다시 설정 유효성 검사

정책  편집 **창에서** Office  문서 액세스 제어 옆에 있는 편집을 선택하고, 사용자가 모바일 장치에서 Office 파일에 액세스하는 방법 관리를 확장하고, 실패한 시도 횟수가 일부 수로 설정된 **후 PIN** 재설정을 확정합니다.  기본적으로 5입니다. 
  
1. 사용자의 Android 장치에서 Outlook 열고 사용자의 Microsoft 365 Business Premium 자격 증명으로 로그인합니다.
    
2. 정책에 지정된 횟수만큼 잘못된 PIN을 입력합니다. PIN 시도 제한에 도달하여 **PIN을** 다시 설정하라는 메시지가 표시될 수 있습니다. 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../../media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. **PIN 다시 설정** 을 누릅니다. 사용자의 자격 증명으로 로그인하라는 메시지가 Microsoft 365 Business Premium 새 PIN을 설정해야 합니다.
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>사용자가 모든 작업 파일을 비즈니스용 OneDrive에 저장하도록 강제 적용 유효성 검사

**정책 편집** 창에서 **분실했거나 도난당한 장치 보호** 옆의 **편집** 을 선택하고 **장치를 분실하거나 도난당한 경우 작업 파일 보호** 를 확장한 다음 **사용자가 모든 작업 파일을 비즈니스용 OneDrive에 저장하도록 강제 적용** 이 **켜기** 로 설정되어 있는지 확인합니다.
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. 사용자의 Android 장치에서 Outlook 열고 사용자의 Microsoft 365 Business Premium 자격 증명으로 로그인하고 요청된 경우 PIN을 입력합니다.
    
2. 첨부 파일이 포함된 전자 메일을 열고 첨부 파일 정보 옆의 아래쪽 화살표 아이콘을 탭합니다.
    
    ![Tap the down arrow next to an attachment to try to save it.](../../media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    화면 아래쪽에 **디바이스에** 저장할 수 없습니다.가 표시됩니다. 
    
    ![Warning text that indicates cannot save a file locally to an Android.](../../media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > 현재 Android에서는 비즈니스용 OneDrive에 저장하는 기능을 사용할 수 없으므로 '로컬 저장이 차단되었습니다'만 표시됩니다. 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>Office 앱이 지정된 시간 동안 유휴 상태인 경우 사용자 다시 로그인 필요 유효성 검사

정책  편집 **창에서** Office 문서 액세스 제어 옆의 편집을 선택하고, 사용자가 모바일 장치에서 Office 파일에 액세스하는 방법  관리를 확장하고, Office 앱이 유휴로 설정된 후 사용자가 다시 로그인해야 하는지 확인을 몇 분으로 설정해야 합니다.  기본적으로 30분입니다. 
  
1. 사용자의 Android 장치에서 Outlook 열고 사용자의 Microsoft 365 Business Premium 자격 증명으로 로그인하고 요청된 경우 PIN을 입력합니다.
    
2. 이제 Outlook의 받은 편지함이 표시됩니다. Android 장치를 최소 30분(또는 정책에서 지정한 시간 이상) 동안 사용하지 않고 그대로 두어 장치가 유휴 상태로 전환되도록 합니다. 장치 화면이 어두워질 수 있습니다.
    
3. Android Outlook 다시 액세스합니다.
    
4. PIN을 다시 액세스하기 전에 PIN을 입력하라는 메시지가 Outlook 있습니다.
    
### <a name="validate-protect-work-files-with-encryption"></a>암호화로 작업 파일 보호 유효성 검사

**정책 편집** 창에서 **분실했거나 도난당한 장치 보호** 옆의 **편집** 을 선택하고 **장치를 분실하거나 도난당한 경우 작업 파일 보호** 를 확장한 다음 **암호화로 작업 파일 보호** 가 **켜기** 로 설정되어 있고 **사용자가 모든 작업 파일을 비즈니스용 OneDrive에 저장하도록 강제 적용** 이 **끄기** 로 설정되어 있는지 확인합니다.
  
1. 사용자의 Android 장치에서 Outlook 열고 사용자의 Microsoft 365 Business Premium 자격 증명으로 로그인하고 요청된 경우 PIN을 입력합니다.
    
2. 몇 개의 이미지 파일 첨부 파일이 포함된 전자 메일을 니다.
    
3. 첨부 파일 정보 옆의 아래쪽 화살표 아이콘을 탭하여 파일을 저장합니다.
    
    ![Tap the down arrow to save the figure file to the Android device.](../../media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. 장치의 사진, 미디어 및 파일에 액세스하기 위해 Outlook을 허용하라는 메시지가 표시될 수 있습니다. **허용** 을 탭합니다.
    
5. 화면 아래쪽에서 **장치에 저장** 을 선택한 다음 **갤러리** 앱을 엽니다. 
    
6. 목록에 암호화된 사진 1장(이미지 첨부 파일을 여러 장 저장한 경우 1장 이상)이 표시됩니다. 암호화된 사진은 사진 목록에 회색 정사각형으로 표시되며 정사각형 중앙에는 흰색 원 안의 느낌표 아이콘이 나타납니다.
    
    ![An encrypted image file in the Gallery app.](../../media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="ios"></a>iOS
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>사용자 장치에서 앱 보호 설정이 작동하는지 확인

[iOS 장치에 대한 앱 구성을 설정](app-protection-settings-for-android-and-ios.md) 한 후 앱을 보호하려면 다음 단계를 따라 선택한 설정이 작동하는지 확인하세요. 
  
먼저 정책이 유효성을 검사할 앱에 적용해야 합니다.
  
1. Microsoft 365 Business Premium [관리 센터에서](https://admin.microsoft.com)정책 편집  \> **정책으로 이동하세요.**
    
2. 설치 시 만든 설정에 **대한 iOS용** 응용 프로그램 정책 또는 만든 다른 정책을 선택하고 응용 프로그램에 대해 Outlook 확인합니다. 
    
    ![Shows all the apps for which this policy protects files.](../../media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a>Office 앱 액세스에 PIN 필요 유효성 검사

**정책 편집** 창에서 **Office 문서 액세스 제어** 옆의 **편집** 을 선택하고 **사용자가 모바일 장치에서 Office 파일에 액세스하는 방법 관리** 를 확장한 다음 **Office 앱 액세스에 PIN 또는 지문 필요** 가 **켜기** 로 설정되어 있는지 확인합니다.
  
![앱에 액세스하려면 PIN 또는 지문 필요 Office 설정되어 있는지 확인 합니다.](../../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. 사용자의 iOS 장치에서 Outlook 열고 사용자의 Microsoft 365 Business Premium 자격 증명으로 로그인합니다.
    
2. PIN을 입력하거나 지문을 사용하라는 메시지가 표시될 수도 있습니다.
    
    ![Enter a PIN on your IOS device to access Office apps.](../../media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>시도가 몇 번 실패한 후 PIN 다시 설정 유효성 검사

정책  편집 **창에서** Office  문서 액세스 제어 옆에 있는 편집을 선택하고, 사용자가 모바일 장치에서 Office 파일에 액세스하는 방법 관리를 확장하고, 실패한 시도 횟수가 일부 수로 설정된 **후 PIN** 재설정을 확정합니다.  기본적으로 5입니다. 
  
1. 사용자의 iOS 장치에서 Outlook 열고 사용자의 Microsoft 365 Business Premium 자격 증명으로 로그인합니다.
    
2. 정책에 지정된 횟수만큼 잘못된 PIN을 입력합니다. PIN 시도 제한에 도달하여 **PIN을** 다시 설정하라는 메시지가 표시될 수 있습니다. 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../../media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. **확인** 을 누릅니다. 사용자의 자격 증명으로 로그인하라는 메시지가 Microsoft 365 Business Premium 새 PIN을 설정해야 합니다.
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>사용자가 모든 작업 파일을 비즈니스용 OneDrive에 저장하도록 강제 적용 유효성 검사

**정책 편집** 창에서 **분실했거나 도난당한 장치 보호** 옆의 **편집** 을 선택하고 **장치를 분실하거나 도난당한 경우 작업 파일 보호** 를 확장한 다음 **사용자가 모든 작업 파일을 비즈니스용 OneDrive에 저장하도록 강제 적용** 이 **켜기** 로 설정되어 있는지 확인합니다.
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. 사용자의 iOS 장치에서 Outlook 열고 사용자의 Microsoft 365 Business Premium 자격 증명으로 로그인하고 요청된 경우 PIN을 입력합니다.
    
2. 첨부 파일이 포함된 전자 메일을 연 다음 첨부 파일을 열고 화면 아래쪽에 있는 **저장** 을 선택합니다. 
    
    ![Tap the Save option after you open an attachment to try to save it.](../../media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. 비즈니스용 OneDrive에 대한 옵션만 표시됩니다. 그렇지 않은 경우 계정 **추가를** 탭하고 계정 **비즈니스용 OneDrive** 추가 화면에서 Storage **선택합니다.** 메시지가 표시될 때 최종 Microsoft 365 Business Premium 로그인할 수 있는 사용자를 제공합니다. 
    
    **저장** 을 탭하고 **비즈니스용 OneDrive** 를 선택합니다.
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>Office 앱이 지정된 시간 동안 유휴 상태인 경우 사용자 다시 로그인 필요 유효성 검사

정책  편집 **창에서** Office 문서 액세스 제어 옆의 편집을 선택하고, 사용자가 모바일 장치에서 Office 파일에 액세스하는 방법  관리를 확장하고, Office 앱이 유휴로 설정된 후 사용자가 다시 로그인해야 하는지 확인을 몇 분으로 설정해야 합니다.  기본적으로 30분입니다. 
  
1. 사용자의 iOS 장치에서 Outlook 열고 사용자의 Microsoft 365 Business Premium 자격 증명으로 로그인하고 요청된 경우 PIN을 입력합니다.
    
2. 이제 Outlook의 받은 편지함이 표시됩니다. iOS 장치를 최소 30분(또는 정책에서 지정한 시간 이상) 동안 사용하지 않고 그대로 둡니다. 장치 화면이 어두워질 수 있습니다.
    
3. iOS Outlook 다시 액세스합니다.
    
4. PIN을 다시 액세스하기 전에 PIN을 입력하라는 메시지가 Outlook 있습니다.
    
### <a name="validate-protect-work-files-with-encryption"></a>암호화로 작업 파일 보호 유효성 검사

**정책 편집** 창에서 **분실했거나 도난당한 장치 보호** 옆의 **편집** 을 선택하고 **장치를 분실하거나 도난당한 경우 작업 파일 보호** 를 확장한 다음 **암호화로 작업 파일 보호** 가 **켜기** 로 설정되어 있고 **사용자가 모든 작업 파일을 비즈니스용 OneDrive에 저장하도록 강제 적용** 이 **끄기** 로 설정되어 있는지 확인합니다.
  
1. 사용자의 iOS 장치에서 Outlook 열고 사용자의 Microsoft 365 Business Premium 자격 증명으로 로그인하고 요청된 경우 PIN을 입력합니다.
    
2. 몇 개의 이미지 파일 첨부 파일이 포함된 전자 메일을 니다.
    
3. 첨부 파일을 탭한 다음 파일 아래에서 **저장** 옵션을 탭합니다. 
    
4. 홈 화면에서 **사진** 앱을 엽니다. 암호화되어 저장된 사진 1장(이미지 첨부 파일을 여러 장 저장한 경우 1장 이상)이 표시됩니다. 
    
---

