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
ms.openlocfilehash: 43e74b548711550090021c39096b1647cee9e039
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339333"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a><span data-ttu-id="eaa22-103">Android 또는 iOS 장치에서 앱 보호 설정 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="eaa22-103">Validate app protection settings on Android or iOS devices</span></span>

<span data-ttu-id="eaa22-104">다음 섹션의 지침에 따라 Android 또는 iOS 장치에서 앱 보호 설정의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-104">Follow the instructions in the following sections to validate app protection settings on Android or iOS devices.</span></span>
  
## <a name="android"></a><span data-ttu-id="eaa22-105">Android</span><span class="sxs-lookup"><span data-stu-id="eaa22-105">Android</span></span>
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="eaa22-106">사용자 장치에서 앱 보호 설정이 작동하고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="eaa22-106">Check that the app protection settings are working on user devices</span></span>

<span data-ttu-id="eaa22-107">[Android 장치에 대한 앱 구성을 설정](app-protection-settings-for-android-and-ios.md) 한 후 앱을 보호하려면 다음 단계를 따라 선택한 설정이 작동하는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="eaa22-107">After you [set app configurations for Android devices](app-protection-settings-for-android-and-ios.md) to protect the apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="eaa22-108">먼저 정책이 유효성을 검사할 앱에 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-108">First, make sure that the policy applies to the app in which you're going to validate it.</span></span>
  
1. <span data-ttu-id="eaa22-109">Microsoft 365 Business Premium [관리 센터에서](https://admin.microsoft.com)정책 편집  \> **정책으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="eaa22-109">In the Microsoft 365 Business Premium [admin center](https://admin.microsoft.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="eaa22-110">설치 시 만든 설정에 **대해 Android용** 응용 프로그램 정책 또는 만든 다른 정책을 선택하고 응용 프로그램에 Outlook 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-110">Choose **Application policy for Android** for the settings you created at setup, or another policy you created, and verify that it's enforced for Outlook, for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](../media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a><span data-ttu-id="eaa22-112">Office 앱 액세스에 PIN 또는 지문 필요 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="eaa22-112">Validate Require a PIN or a fingerprint to access Office apps</span></span>

<span data-ttu-id="eaa22-113">**정책 편집** 창에서 **Office 문서 액세스 제어** 옆의 **편집** 을 선택하고 **사용자가 모바일 장치에서 Office 파일에 액세스하는 방법 관리** 를 확장한 다음 **Office 앱 액세스에 PIN 또는 지문 필요** 가 **켜기** 로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-113">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![앱에 액세스하려면 PIN 또는 지문 필요 Office 설정되어 있는지 확인 합니다.](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="eaa22-115">사용자의 Android 장치에서 Outlook 열고 사용자의 Microsoft 365 Business Premium 자격 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-115">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="eaa22-116">PIN을 입력하거나 지문을 사용하라는 메시지가 표시될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-116">You'll also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your Android device to access Office apps.](../media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="eaa22-118">시도가 몇 번 실패한 후 PIN 다시 설정 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="eaa22-118">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="eaa22-119">정책  편집 **창에서** Office  문서 액세스 제어 옆에 있는 편집을 선택하고, 사용자가 모바일 장치에서 Office 파일에 액세스하는 방법 관리를 확장하고, 실패한 시도 횟수가 일부 수로 설정된 **후 PIN** 재설정을 확정합니다. </span><span class="sxs-lookup"><span data-stu-id="eaa22-119">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number.</span></span> <span data-ttu-id="eaa22-120">기본적으로 5입니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-120">This is 5 by default.</span></span> 
  
1. <span data-ttu-id="eaa22-121">사용자의 Android 장치에서 Outlook 열고 사용자의 Microsoft 365 Business Premium 자격 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-121">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="eaa22-122">정책에 지정된 횟수만큼 잘못된 PIN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-122">Enter an incorrect PIN as many times as specified by the policy.</span></span> <span data-ttu-id="eaa22-123">PIN 시도 제한에 도달하여 **PIN을** 다시 설정하라는 메시지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-123">You'll see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. <span data-ttu-id="eaa22-125">**PIN 다시 설정** 을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-125">Press **Reset PIN**.</span></span> <span data-ttu-id="eaa22-126">사용자의 자격 증명으로 로그인하라는 메시지가 Microsoft 365 Business Premium 새 PIN을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-126">You'll be prompted to sign in with the user's Microsoft 365 Business Premium credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="eaa22-127">사용자가 모든 작업 파일을 비즈니스용 OneDrive에 저장하도록 강제 적용 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="eaa22-127">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="eaa22-128">**정책 편집** 창에서 **분실했거나 도난당한 장치 보호** 옆의 **편집** 을 선택하고 **장치를 분실하거나 도난당한 경우 작업 파일 보호** 를 확장한 다음 **사용자가 모든 작업 파일을 비즈니스용 OneDrive에 저장하도록 강제 적용** 이 **켜기** 로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-128">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="eaa22-130">사용자의 Android 장치에서 Outlook 열고 사용자의 Microsoft 365 Business Premium 자격 증명으로 로그인하고 요청된 경우 PIN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-130">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="eaa22-131">첨부 파일이 포함된 전자 메일을 열고 첨부 파일 정보 옆의 아래쪽 화살표 아이콘을 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-131">Open an email that contains an attachment and tap the down arrow icon next to the attachment's information.</span></span>
    
    ![Tap the down arrow next to an attachment to try to save it.](../media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    <span data-ttu-id="eaa22-133">화면 아래쪽에 **디바이스에** 저장할 수 없습니다.가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-133">You'll see **Cannot save to device** on the bottom of the screen.</span></span> 
    
    ![Warning text that indicates cannot save a file locally to an Android.](../media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > <span data-ttu-id="eaa22-135">현재 Android에서는 비즈니스용 OneDrive에 저장하는 기능을 사용할 수 없으므로 '로컬 저장이 차단되었습니다'만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-135">Saving to OneDrive for Business is not enabled for Android at this time, so you can only see that saving locally is blocked.</span></span> 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="eaa22-136">Office 앱이 지정된 시간 동안 유휴 상태인 경우 사용자 다시 로그인 필요 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="eaa22-136">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="eaa22-137">정책  편집 **창에서** Office 문서 액세스 제어 옆의 편집을 선택하고, 사용자가 모바일 장치에서 Office 파일에 액세스하는 방법  관리를 확장하고, Office 앱이 유휴로 설정된 후 사용자가 다시 로그인해야 하는지 확인을 몇 분으로 설정해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="eaa22-137">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes.</span></span> <span data-ttu-id="eaa22-138">기본적으로 30분입니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-138">This is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="eaa22-139">사용자의 Android 장치에서 Outlook 열고 사용자의 Microsoft 365 Business Premium 자격 증명으로 로그인하고 요청된 경우 PIN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-139">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="eaa22-p105">이제 Outlook의 받은 편지함이 표시됩니다. Android 장치를 최소 30분(또는 정책에서 지정한 시간 이상) 동안 사용하지 않고 그대로 두어 장치가 유휴 상태로 전환되도록 합니다. 장치 화면이 어두워질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-p105">You should now see Outlook's inbox. Let the Android device idle untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="eaa22-143">Android Outlook 다시 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-143">Access Outlook on the Android device again.</span></span>
    
4. <span data-ttu-id="eaa22-144">PIN을 다시 액세스하기 전에 PIN을 입력하라는 메시지가 Outlook 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-144">You'll be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="eaa22-145">암호화로 작업 파일 보호 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="eaa22-145">Validate Protect work files with encryption</span></span>

<span data-ttu-id="eaa22-146">**정책 편집** 창에서 **분실했거나 도난당한 장치 보호** 옆의 **편집** 을 선택하고 **장치를 분실하거나 도난당한 경우 작업 파일 보호** 를 확장한 다음 **암호화로 작업 파일 보호** 가 **켜기** 로 설정되어 있고 **사용자가 모든 작업 파일을 비즈니스용 OneDrive에 저장하도록 강제 적용** 이 **끄기** 로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-146">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="eaa22-147">사용자의 Android 장치에서 Outlook 열고 사용자의 Microsoft 365 Business Premium 자격 증명으로 로그인하고 요청된 경우 PIN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-147">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="eaa22-148">몇 개의 이미지 파일 첨부 파일이 포함된 전자 메일을 니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-148">Open an email that contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="eaa22-149">첨부 파일 정보 옆의 아래쪽 화살표 아이콘을 탭하여 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-149">Tap the down arrow icon next to the attachment's info to save it.</span></span>
    
    ![Tap the down arrow to save the figure file to the Android device.](../media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. <span data-ttu-id="eaa22-p106">장치의 사진, 미디어 및 파일에 액세스하기 위해 Outlook을 허용하라는 메시지가 표시될 수 있습니다. **허용** 을 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-p106">You may be prompted to allow Outlook to access photos, media, and files on your device. Tap **Allow**.</span></span>
    
5. <span data-ttu-id="eaa22-153">화면 아래쪽에서 **장치에 저장** 을 선택한 다음 **갤러리** 앱을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-153">At the bottom of the screen, choose to **Save to Device** and then open the **Gallery** app.</span></span> 
    
6. <span data-ttu-id="eaa22-p107">목록에 암호화된 사진 1장(이미지 첨부 파일을 여러 장 저장한 경우 1장 이상)이 표시됩니다. 암호화된 사진은 사진 목록에 회색 정사각형으로 표시되며 정사각형 중앙에는 흰색 원 안의 느낌표 아이콘이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-p107">You should see an encrypted photo (or more, if you saved multiple image file attachments) in the list. It may appear in the Pictures list as a gray square with a white exclamation point within a white circle in the center of the gray square.</span></span>
    
    ![An encrypted image file in the Gallery app.](../media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="ios"></a><span data-ttu-id="eaa22-157">iOS</span><span class="sxs-lookup"><span data-stu-id="eaa22-157">iOS</span></span>
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="eaa22-158">사용자 장치에서 앱 보호 설정이 작동하는지 확인</span><span class="sxs-lookup"><span data-stu-id="eaa22-158">Check that the App protection settings are working on user devices</span></span>

<span data-ttu-id="eaa22-159">[iOS 장치에 대한 앱 구성을 설정](app-protection-settings-for-android-and-ios.md) 한 후 앱을 보호하려면 다음 단계를 따라 선택한 설정이 작동하는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="eaa22-159">After you [set app configurations for iOS devices](app-protection-settings-for-android-and-ios.md) to protect apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="eaa22-160">먼저 정책이 유효성을 검사할 앱에 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-160">First, make sure that the policy applies to the app in which you're going to validate it.</span></span>
  
1. <span data-ttu-id="eaa22-161">Microsoft 365 Business Premium [관리 센터에서](https://admin.microsoft.com)정책 편집  \> **정책으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="eaa22-161">In the Microsoft 365 Business Premium [admin center](https://admin.microsoft.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="eaa22-162">설치 시 만든 설정에 **대한 iOS용** 응용 프로그램 정책 또는 만든 다른 정책을 선택하고 응용 프로그램에 대해 Outlook 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-162">Choose **Application policy for iOS** for the settings you created at setup, or another policy you created, and verify that it's enforced for Outlook for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](../media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a><span data-ttu-id="eaa22-164">Office 앱 액세스에 PIN 필요 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="eaa22-164">Validate Require a PIN to access Office apps</span></span>

<span data-ttu-id="eaa22-165">**정책 편집** 창에서 **Office 문서 액세스 제어** 옆의 **편집** 을 선택하고 **사용자가 모바일 장치에서 Office 파일에 액세스하는 방법 관리** 를 확장한 다음 **Office 앱 액세스에 PIN 또는 지문 필요** 가 **켜기** 로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-165">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![앱에 액세스하려면 PIN 또는 지문 필요 Office 설정되어 있는지 확인 합니다.](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="eaa22-167">사용자의 iOS 장치에서 Outlook 열고 사용자의 Microsoft 365 Business Premium 자격 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-167">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="eaa22-168">PIN을 입력하거나 지문을 사용하라는 메시지가 표시될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-168">You'll also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your IOS device to access Office apps.](../media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="eaa22-170">시도가 몇 번 실패한 후 PIN 다시 설정 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="eaa22-170">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="eaa22-171">정책  편집 **창에서** Office  문서 액세스 제어 옆에 있는 편집을 선택하고, 사용자가 모바일 장치에서 Office 파일에 액세스하는 방법 관리를 확장하고, 실패한 시도 횟수가 일부 수로 설정된 **후 PIN** 재설정을 확정합니다. </span><span class="sxs-lookup"><span data-stu-id="eaa22-171">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number.</span></span> <span data-ttu-id="eaa22-172">기본적으로 5입니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-172">This is 5 by default.</span></span> 
  
1. <span data-ttu-id="eaa22-173">사용자의 iOS 장치에서 Outlook 열고 사용자의 Microsoft 365 Business Premium 자격 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-173">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="eaa22-174">정책에 지정된 횟수만큼 잘못된 PIN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-174">Enter an incorrect PIN as many times as specified by the policy.</span></span> <span data-ttu-id="eaa22-175">PIN 시도 제한에 도달하여 **PIN을** 다시 설정하라는 메시지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-175">You'll see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. <span data-ttu-id="eaa22-177">**확인** 을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-177">Press **OK**.</span></span> <span data-ttu-id="eaa22-178">사용자의 자격 증명으로 로그인하라는 메시지가 Microsoft 365 Business Premium 새 PIN을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-178">You'll be prompted to sign in with the user's Microsoft 365 Business Premium credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="eaa22-179">사용자가 모든 작업 파일을 비즈니스용 OneDrive에 저장하도록 강제 적용 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="eaa22-179">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="eaa22-180">**정책 편집** 창에서 **분실했거나 도난당한 장치 보호** 옆의 **편집** 을 선택하고 **장치를 분실하거나 도난당한 경우 작업 파일 보호** 를 확장한 다음 **사용자가 모든 작업 파일을 비즈니스용 OneDrive에 저장하도록 강제 적용** 이 **켜기** 로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-180">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="eaa22-182">사용자의 iOS 장치에서 Outlook 열고 사용자의 Microsoft 365 Business Premium 자격 증명으로 로그인하고 요청된 경우 PIN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-182">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="eaa22-183">첨부 파일이 포함된 전자 메일을 연 다음 첨부 파일을 열고 화면 아래쪽에 있는 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-183">Open an email that contains an attachment, open the attachment and choose **Save** on the bottom of the screen.</span></span> 
    
    ![Tap the Save option after you open an attachment to try to save it.](../media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. <span data-ttu-id="eaa22-185">비즈니스용 OneDrive에 대한 옵션만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-185">You should only see an option for OneDrive for Business.</span></span> <span data-ttu-id="eaa22-186">그렇지 않은 경우 계정 **추가를** 탭하고 계정 **비즈니스용 OneDrive** 추가 화면에서 Storage **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eaa22-186">If not, tap **Add Account** and select **OneDrive for Business** from the **Add Storage Account** screen.</span></span> <span data-ttu-id="eaa22-187">메시지가 표시될 때 최종 Microsoft 365 Business Premium 로그인할 수 있는 사용자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-187">Provide the end user's Microsoft 365 Business Premium to sign in when prompted.</span></span> 
    
    <span data-ttu-id="eaa22-188">**저장** 을 탭하고 **비즈니스용 OneDrive** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-188">Tap **Save** and select **OneDrive for Business**.</span></span>
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="eaa22-189">Office 앱이 지정된 시간 동안 유휴 상태인 경우 사용자 다시 로그인 필요 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="eaa22-189">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="eaa22-190">정책  편집 **창에서** Office 문서 액세스 제어 옆의 편집을 선택하고, 사용자가 모바일 장치에서 Office 파일에 액세스하는 방법  관리를 확장하고, Office 앱이 유휴로 설정된 후 사용자가 다시 로그인해야 하는지 확인을 몇 분으로 설정해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="eaa22-190">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes.</span></span> <span data-ttu-id="eaa22-191">기본적으로 30분입니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-191">This is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="eaa22-192">사용자의 iOS 장치에서 Outlook 열고 사용자의 Microsoft 365 Business Premium 자격 증명으로 로그인하고 요청된 경우 PIN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-192">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="eaa22-p113">이제 Outlook의 받은 편지함이 표시됩니다. iOS 장치를 최소 30분(또는 정책에서 지정한 시간 이상) 동안 사용하지 않고 그대로 둡니다. 장치 화면이 어두워질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-p113">You should now see Outlook's inbox. Let the iOS device untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="eaa22-196">iOS Outlook 다시 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-196">Access Outlook on the iOS device again.</span></span>
    
4. <span data-ttu-id="eaa22-197">PIN을 다시 액세스하기 전에 PIN을 입력하라는 메시지가 Outlook 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-197">You'll be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="eaa22-198">암호화로 작업 파일 보호 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="eaa22-198">Validate Protect work files with encryption</span></span>

<span data-ttu-id="eaa22-199">**정책 편집** 창에서 **분실했거나 도난당한 장치 보호** 옆의 **편집** 을 선택하고 **장치를 분실하거나 도난당한 경우 작업 파일 보호** 를 확장한 다음 **암호화로 작업 파일 보호** 가 **켜기** 로 설정되어 있고 **사용자가 모든 작업 파일을 비즈니스용 OneDrive에 저장하도록 강제 적용** 이 **끄기** 로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-199">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="eaa22-200">사용자의 iOS 장치에서 Outlook 열고 사용자의 Microsoft 365 Business Premium 자격 증명으로 로그인하고 요청된 경우 PIN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-200">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="eaa22-201">몇 개의 이미지 파일 첨부 파일이 포함된 전자 메일을 니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-201">Open an email that contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="eaa22-202">첨부 파일을 탭한 다음 파일 아래에서 **저장** 옵션을 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-202">Tap the attachment and then tap the **Save** option under it.</span></span> 
    
4. <span data-ttu-id="eaa22-p114">홈 화면에서 **사진** 앱을 엽니다. 암호화되어 저장된 사진 1장(이미지 첨부 파일을 여러 장 저장한 경우 1장 이상)이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaa22-p114">Open **Photos** app from the home screen. You should see an encrypted photo (or more, if you saved multiple image file attachments) saved, but encrypted.</span></span> 
    
---

