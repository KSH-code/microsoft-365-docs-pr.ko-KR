---
title: Android 또는 iOS 장치에서 앱 보호 설정 유효성 검사
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: 'Learn how to validate the Microsoft 365 Business app protection settings in your Android or iOS devices.  '
ms.openlocfilehash: 5ab16d481bd11ec31a1387a7e94d8b08bb3e0abe
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287366"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a><span data-ttu-id="43d46-103">Android 또는 iOS 장치에서 앱 보호 설정 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="43d46-103">Validate app protection settings on Android or iOS devices</span></span>

<span data-ttu-id="43d46-104">Android 또는 iOS 장치에서 앱 보호 설정의 유효성을 검사 하려면 탭의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="43d46-104">Follow the instructions in the tabs to validate app protection settings on Android or iOS devices.</span></span>
  
## <a name="androidtab"></a>[<span data-ttu-id="43d46-105">Android</span><span class="sxs-lookup"><span data-stu-id="43d46-105">Android</span></span>](#tab/)
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="43d46-106">사용자 장치에서 앱 보호 설정이 작동하는지 확인</span><span class="sxs-lookup"><span data-stu-id="43d46-106">Check that the App protection settings are working on user devices</span></span>

<span data-ttu-id="43d46-107">[Android 장치에 대한 앱 구성을 설정](app-protection-settings-for-android-and-ios.md) 한 후 앱을 보호하려면 다음 단계를 따라 선택한 설정이 작동하는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="43d46-107">After you [set app configurations for Android devices](app-protection-settings-for-android-and-ios.md) to protect the apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="43d46-108">우선, 유효성을 검사할 앱에 정책이 적용되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-108">First, make sure that the policy applies to the app in which you are going to validate it.</span></span>
  
1. <span data-ttu-id="43d46-109">Microsoft 365 Business [관리 센터](https://portal.office.com)에서 **정책** \> **정책 편집**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-109">In the Microsoft 365 Business [admin center](https://portal.office.com) go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="43d46-110">설정에 대해 **Android에 대한 응용 프로그램 정책** 또는 생성한 다른 정책을 선택하고 Outlook과 같은 프로그램에 적용되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-110">Choose **Application policy for Android** for the settings you created at setup, or another policy you created, and verify that it is enforced for Outlook for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a><span data-ttu-id="43d46-112">Office 앱 액세스에 PIN 또는 지문 필요 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="43d46-112">Validate Require a PIN or a fingerprint to access Office apps</span></span>

<span data-ttu-id="43d46-113">**정책 편집** 창에서 **Office 문서 액세스 제어** 옆의 **편집**을 선택하고 **사용자가 모바일 장치에서 Office 파일에 액세스하는 방법 관리**를 확장한 다음 **Office 앱 액세스에 PIN 또는 지문 필요**가 **켜기**로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-113">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Make sure that the Require a PIN or fingerprint to acces Office apps is set to On.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="43d46-115">사용자의 Android 장치에서 Outlook을 열고 사용자의 Microsoft 365 Business 자격 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-115">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="43d46-116">PIN을 입력하거나 지문을 사용하라는 메시지도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-116">You will also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your Android device to access Office apps.](media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="43d46-118">시도가 몇 번 실패한 후 PIN 다시 설정 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="43d46-118">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="43d46-119">**정책 편집** 창에서 **Office 문서 액세스 제어** 옆의 **편집**을 선택하고 **사용자가 모바일 장치에서 Office 파일에 액세스하는 방법 관리**를 확장한 다음 **시도가 몇 번 실패한 후 PIN 다시 설정**에 숫자가 설정되어 있는지 확인합니다. 이 숫자의 기본값은 5입니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-119">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number - this is 5 by default.</span></span> 
  
1. <span data-ttu-id="43d46-120">사용자의 Android 장치에서 Outlook을 열고 사용자의 Microsoft 365 Business 자격 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-120">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="43d46-p101">정책에 지정된 횟수만큼 잘못된 PIN을 입력합니다. **PIN 시도 제한 도달**로 인해 PIN을 다시 설정하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-p101">Enter an incorrect PIN as many times as specified by the policy. You will see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. <span data-ttu-id="43d46-p102">**PIN 다시 설정**을 누릅니다. 사용자의 Microsoft 365 Business 자격 증명으로 로그인하라는 메시지가 표시되며 로그인 후 새 PIN을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-p102">Press **Reset PIN**. You will be prompted to sign in with the user's Microsoft 365 Business credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="43d46-126">사용자가 모든 작업 파일을 비즈니스용 OneDrive에 저장하도록 강제 적용 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="43d46-126">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="43d46-127">**정책 편집** 창에서 **분실했거나 도난당한 장치 보호** 옆의 **편집**을 선택하고 **장치를 분실하거나 도난당한 경우 작업 파일 보호**를 확장한 다음 **사용자가 모든 작업 파일을 비즈니스용 OneDrive에 저장하도록 강제 적용**이 **켜기**로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-127">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="43d46-129">사용자의 Android 장치에서 Outlook을 열고 사용자의 Microsoft 365 Business 자격 증명으로 로그인한 다음 요청된 경우 PIN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-129">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="43d46-130">첨부 파일이 포함된 전자 메일을 열고 첨부 파일 정보 옆의 아래쪽 화살표 아이콘을 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-130">Open an email that contains an attachment and tap the down arrow icon next to the attachment's information.</span></span>
    
    ![Tap the down arrow next to an attachment to try to save it.](media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    <span data-ttu-id="43d46-132">화면 아래쪽에 **장치에 저장할 수 없음** 문구가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-132">You will see **Cannot save to device** on the bottom of the screen.</span></span> 
    
    ![Warning text that indicates cannot save a file locally to an Android.](media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > <span data-ttu-id="43d46-134">현재 Android에서는 비즈니스용 OneDrive에 저장하는 기능을 사용할 수 없으므로 '로컬 저장이 차단되었습니다'만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-134">Saving to OneDrive for Business is not enabled for Android at this time, so you can only see that saving locally is blocked.</span></span> 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="43d46-135">Office 앱이 지정된 시간 동안 유휴 상태인 경우 사용자 다시 로그인 필요 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="43d46-135">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="43d46-136">**정책 편집** 창에서 **Office 문서 액세스 제어** 옆의 **편집**을 선택하고 **사용자가 모바일 장치에서 Office 파일에 액세스하는 방법 관리**를 확장한 다음 **Office 앱이 이 시간 동안 유휴 상태인 경우 사용자 다시 로그인 필요**에 분단위의 숫자가 설정되어 있는지 확인합니다. 이 숫자의 기본값은 30분입니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-136">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes - this is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="43d46-137">사용자의 Android 장치에서 Outlook을 열고 사용자의 Microsoft 365 Business 자격 증명으로 로그인한 다음 요청된 경우 PIN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-137">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="43d46-p103">이제 Outlook의 받은 편지함이 표시됩니다. Android 장치를 최소 30분(또는 정책에서 지정한 시간 이상) 동안 사용하지 않고 그대로 두어 장치가 유휴 상태로 전환되도록 합니다. 장치 화면이 어두워질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-p103">You should now see Outlook's inbox. Let the Android device idle untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="43d46-141">Android 장치에서 Outlook에 다시 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-141">Re-access Outlook on the Android device.</span></span>
    
4. <span data-ttu-id="43d46-142">Outlook에 다시 액세스하기 전 PIN을 입력하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-142">You will be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="43d46-143">암호화로 작업 파일 보호 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="43d46-143">Validate Protect work files with encryption</span></span>

<span data-ttu-id="43d46-144">**정책 편집** 창에서 **분실했거나 도난당한 장치 보호** 옆의 **편집**을 선택하고 **장치를 분실하거나 도난당한 경우 작업 파일 보호**를 확장한 다음 **암호화로 작업 파일 보호**가 **켜기**로 설정되어 있고 **사용자가 모든 작업 파일을 비즈니스용 OneDrive에 저장하도록 강제 적용**이 **끄기**로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-144">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="43d46-145">사용자의 Android 장치에서 Outlook을 열고 사용자의 Microsoft 365 Business 자격 증명으로 로그인한 다음 요청된 경우 PIN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-145">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="43d46-146">몇 가지 이미지 첨부 파일이 포함된 전자 메일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-146">Open an email which contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="43d46-147">첨부 파일 정보 옆의 아래쪽 화살표 아이콘을 탭하여 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-147">Tap the down arrow icon next to the attachment's info to save it.</span></span>
    
    ![Tap the down arrow to save the figure file to the Android device.](media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. <span data-ttu-id="43d46-p104">장치의 사진, 미디어 및 파일에 액세스하기 위해 Outlook을 허용하라는 메시지가 표시될 수 있습니다. **허용**을 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-p104">You may be prompted to allow Outlook to access photos, media, and files on your device. Tap **Allow**.</span></span>
    
5. <span data-ttu-id="43d46-151">화면 아래쪽에서 **장치에 저장**을 선택한 다음 **갤러리** 앱을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-151">At the bottom of the screen, choose to **Save to Device** and then open the **Gallery** app.</span></span> 
    
6. <span data-ttu-id="43d46-p105">목록에 암호화된 사진 1장(이미지 첨부 파일을 여러 장 저장한 경우 1장 이상)이 표시됩니다. 암호화된 사진은 사진 목록에 회색 정사각형으로 표시되며 정사각형 중앙에는 흰색 원 안의 느낌표 아이콘이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-p105">You should see an encrypted photo (or more, if you saved multiple image file attachments) in the list. It may appear in the Pictures list as a gray square with a white exclamation point within a white circle in the center of the gray square.</span></span>
    
    ![An encrypted image file in the Gallery app.](media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="iostab"></a>[<span data-ttu-id="43d46-155">iOS</span><span class="sxs-lookup"><span data-stu-id="43d46-155">iOS</span></span>](#tab/)
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="43d46-156">사용자 장치에서 앱 보호 설정이 작동하는지 확인</span><span class="sxs-lookup"><span data-stu-id="43d46-156">Check that the App protection settings are working on user devices</span></span>

<span data-ttu-id="43d46-157">[iOS 장치에 대한 앱 구성을 설정](app-protection-settings-for-android-and-ios.md) 한 후 앱을 보호하려면 다음 단계를 따라 선택한 설정이 작동하는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="43d46-157">After you [set app configurations for iOS devices](app-protection-settings-for-android-and-ios.md) to protect apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="43d46-158">우선, 유효성을 검사할 앱에 정책이 적용되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-158">First, make sure that the policy applies to the app in which you are going to validate it.</span></span>
  
1. <span data-ttu-id="43d46-159">Microsoft 365 Business [관리 센터](https://portal.office.com)에서 **정책** \> **정책 편집**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-159">In the Microsoft 365 Business [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="43d46-160">설정에 대해 **iOS에 대한 응용 프로그램 정책** 또는 생성한 다른 정책을 선택하고 Outlook과 같은 프로그램에 적용되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-160">Choose **Application policy for iOS** for the settings you created at setup, or another policy you created, and verify that it is enforced for Outlook for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a><span data-ttu-id="43d46-162">Office 앱 액세스에 PIN 필요 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="43d46-162">Validate Require a PIN to access Office apps</span></span>

<span data-ttu-id="43d46-163">**정책 편집** 창에서 **Office 문서 액세스 제어** 옆의 **편집**을 선택하고 **사용자가 모바일 장치에서 Office 파일에 액세스하는 방법 관리**를 확장한 다음 **Office 앱 액세스에 PIN 또는 지문 필요**가 **켜기**로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-163">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Make sure that the Require a PIN or fingerprint to acces Office apps is set to On.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="43d46-165">사용자의 iOS 장치에서 Outlook을 열고 사용자의 Microsoft 365 Business 자격 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-165">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="43d46-166">PIN을 입력하거나 지문을 사용하라는 메시지도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-166">You will also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your IOS device to access Office apps.](media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="43d46-168">시도가 몇 번 실패한 후 PIN 다시 설정 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="43d46-168">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="43d46-169">**정책 편집** 창에서 **Office 문서 액세스 제어** 옆의 **편집**을 선택하고 **사용자가 모바일 장치에서 Office 파일에 액세스하는 방법 관리**를 확장한 다음 **시도가 몇 번 실패한 후 PIN 다시 설정**에 숫자가 설정되어 있는지 확인합니다. 이 숫자의 기본값은 5입니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-169">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number - this is 5 by default.</span></span> 
  
1. <span data-ttu-id="43d46-170">사용자의 iOS 장치에서 Outlook을 열고 사용자의 Microsoft 365 Business 자격 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-170">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="43d46-p106">정책에 지정된 횟수만큼 잘못된 PIN을 입력합니다. **PIN 시도 제한 도달**로 인해 PIN을 다시 설정하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-p106">Enter an incorrect PIN as many times as specified by the policy. You will see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. <span data-ttu-id="43d46-p107">**확인**을 누릅니다. 사용자의 Microsoft 365 Business 자격 증명으로 로그인하라는 메시지가 표시되며 로그인 후 새 PIN을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-p107">Press **OK**. You will be prompted to sign in with the user's Microsoft 365 Business credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="43d46-176">사용자가 모든 작업 파일을 비즈니스용 OneDrive에 저장하도록 강제 적용 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="43d46-176">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="43d46-177">**정책 편집** 창에서 **분실했거나 도난당한 장치 보호** 옆의 **편집**을 선택하고 **장치를 분실하거나 도난당한 경우 작업 파일 보호**를 확장한 다음 **사용자가 모든 작업 파일을 비즈니스용 OneDrive에 저장하도록 강제 적용**이 **켜기**로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-177">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="43d46-179">사용자의 iOS 장치에서 Outlook을 열고 사용자의 Microsoft 365 Business 자격 증명으로 로그인한 다음 요청된 경우 PIN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-179">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="43d46-180">첨부 파일이 포함된 전자 메일을 연 다음 첨부 파일을 열고 화면 아래쪽에 있는 **저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-180">Open an email that contains an attachment, open the attachment and choose **Save** on the bottom of the screen.</span></span> 
    
    ![Tap the Save option after you open an attachment to try to save it.](media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. <span data-ttu-id="43d46-p108">비즈니스용 OneDrive에 대한 옵션만 표시됩니다. 그렇지 않은 경우 **저장소 계정 추가** 화면에서 **계정 추가**를 탭하고 **비즈니스용 OneDrive**를 선택합니다. 메시지가 표시되면 최종 사용자의 Microsoft 365 Business를 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-p108">You should only see an option for OneDrive for Business. If not If not, tap **Add Account** and select **OneDrive for Business** from the **Add Storage Account** screen. Provide the end user's Microsoft 365 Business to sign in when prompted.</span></span> 
    
    <span data-ttu-id="43d46-185">**저장**을 탭하고 **비즈니스용 OneDrive**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-185">Tap **Save** and select **OneDrive for Business**.</span></span>
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="43d46-186">Office 앱이 지정된 시간 동안 유휴 상태인 경우 사용자 다시 로그인 필요 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="43d46-186">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="43d46-187">**정책 편집** 창에서 **Office 문서 액세스 제어** 옆의 **편집**을 선택하고 **사용자가 모바일 장치에서 Office 파일에 액세스하는 방법 관리**를 확장한 다음 **Office 앱이 이 시간 동안 유휴 상태인 경우 사용자 다시 로그인 필요**에 분단위의 숫자가 설정되어 있는지 확인합니다. 이 숫자의 기본값은 30분입니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-187">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes - this is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="43d46-188">사용자의 iOS 장치에서 Outlook을 열고 사용자의 Microsoft 365 Business 자격 증명으로 로그인한 다음 요청된 경우 PIN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-188">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="43d46-p109">이제 Outlook의 받은 편지함이 표시됩니다. iOS 장치를 최소 30분(또는 정책에서 지정한 시간 이상) 동안 사용하지 않고 그대로 둡니다. 장치 화면이 어두워질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-p109">You should now see Outlook's inbox. Let the iOS device untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="43d46-192">iOS 장치에서 Outlook에 다시 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-192">Re-access Outlook on the iOS device.</span></span>
    
4. <span data-ttu-id="43d46-193">Outlook에 다시 액세스하기 전 PIN을 입력하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-193">You will be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="43d46-194">암호화로 작업 파일 보호 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="43d46-194">Validate Protect work files with encryption</span></span>

<span data-ttu-id="43d46-195">**정책 편집** 창에서 **분실했거나 도난당한 장치 보호** 옆의 **편집**을 선택하고 **장치를 분실하거나 도난당한 경우 작업 파일 보호**를 확장한 다음 **암호화로 작업 파일 보호**가 **켜기**로 설정되어 있고 **사용자가 모든 작업 파일을 비즈니스용 OneDrive에 저장하도록 강제 적용**이 **끄기**로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-195">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="43d46-196">사용자의 iOS 장치에서 Outlook을 열고 사용자의 Microsoft 365 Business 자격 증명으로 로그인한 다음 요청된 경우 PIN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-196">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="43d46-197">몇 가지 이미지 첨부 파일이 포함된 전자 메일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-197">Open an email which contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="43d46-198">첨부 파일을 탭한 다음 파일 아래에서 **저장** 옵션을 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-198">Tap the attachment and then tap the **Save** option under it.</span></span> 
    
4. <span data-ttu-id="43d46-p110">홈 화면에서 **사진** 앱을 엽니다. 암호화되어 저장된 사진 1장(이미지 첨부 파일을 여러 장 저장한 경우 1장 이상)이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="43d46-p110">Open **Photos** app from the home screen. You should see an encrypted photo (or more, if you saved multiple image file attachments) saved, but encrypted.</span></span> 
    
---

