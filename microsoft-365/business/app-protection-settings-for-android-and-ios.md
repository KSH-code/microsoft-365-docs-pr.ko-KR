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
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="f9fd5-103">Android 또는 iOS 장치에서 앱 보호 설정 설정하기</span><span class="sxs-lookup"><span data-stu-id="f9fd5-103">Set app protection settings for Android or iOS devices</span></span>

## <a name="create-an-app-management-policy"></a><span data-ttu-id="f9fd5-104">앱 관리 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="f9fd5-104">Create an app management policy</span></span>

1. <span data-ttu-id="f9fd5-105">전역 관리자 자격 증명을 사용하여 [Microsoft 365 Business](https://portal.office.com)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-105">Sign in to [Microsoft 365 Business](https://portal.office.com) with global admin credentials.</span></span> 
    
2. <span data-ttu-id="f9fd5-106">관리 센터의 **장치 정책** 카드에서 **정책 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-106">In the admin center, on the **Device policies** card, choose **Add policy**.</span></span>
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. <span data-ttu-id="f9fd5-108">**정책 추가** 창에서 이 정책의 고유 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="f9fd5-109">**정책 유형**에서 만들려는 정책의 집합에 따라 **Android용 응용 프로그램 관리** 또는 **iOS용 응용 프로그램 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-109">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS** depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="f9fd5-p101">**장치는 분실 또는 도난당 한 경우 암호로 보호 작업 파일** 및 **사용자가 모바일 장치에서 Office 파일을 액세스 하는 방식을 관리할** 확장 \> 하려는 방식 설정을 구성 합니다. 기본적으로 **해제** 되어 **사용자가 모바일 장치에서 Office 파일을 액세스 하는 방식을 관리** 하지만 **에** 설정 하 고 기본값을 적용 하는 것이 좋습니다. 자세한 내용은 [사용할 수 있는 설정](app-protection-settings-for-android-and-ios.md#bkmk_availablesettings) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-p101">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** \> configure the settings how you would like. The **Manage how users access Office files on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values. See [Available settings](app-protection-settings-for-android-and-ios.md#bkmk_availablesettings) for more information.</span></span> 
    
    <span data-ttu-id="f9fd5-113">언제든지 **기본 설정 다시 설정** 링크를 사용하여 기본 설정으로 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-113">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="f9fd5-p102">다음으로 **이러한 설정을 적용할 대상은 누구입니까?** 를 설정하세요. **모든 사용자** 기본 보안 그룹을 사용하지 않으려는 경우 **변경**을 선택하고 이 설정을 적용할 보안 그룹 \> **선택**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-p102">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="f9fd5-117">마지막으로 **완료**를 선택하여 정책을 저장하고 장치를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-117">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="f9fd5-118">앱 관리 정책 편집</span><span class="sxs-lookup"><span data-stu-id="f9fd5-118">Edit an app management policy</span></span>

1. <span data-ttu-id="f9fd5-119">**정책** 카드 **정책 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-119">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="f9fd5-120">**정책 편집** 창에서 변경하려는 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-120">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="f9fd5-p103">정책에서 값을 변경하려는 각 설정 옆의 **편집**을 선택합니다. 변경한 값은 정책에 자동으로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-p103">Choose **Edit** next to each setting to change the values in the policy. When you change a value, it is automatically saved into the policy</span></span> 
    
4. <span data-ttu-id="f9fd5-123">편집을 완료하고 **정책 편집** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-123">When you are finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="f9fd5-124">앱 관리 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="f9fd5-124">Delete an app management policy</span></span>

1. <span data-ttu-id="f9fd5-125">**정책** 카드에서 **정책 삭제**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-125">On the **Policies** card, choose **Delete policy**.</span></span>
    
2. <span data-ttu-id="f9fd5-126">**정책 삭제** 창에서 삭제할 정책 \> **선택**, **확인**을 차례로 선택하여 정책 또는 선택한 정책을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-126">On the **Delete policy** pane, choose the policies you want to delete \> **Select**, then **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="f9fd5-127">사용 가능한 설정</span><span class="sxs-lookup"><span data-stu-id="f9fd5-127">Available settings</span></span>

<span data-ttu-id="f9fd5-128">다음 표에서는 장치에서 작업 파일을 보호하기 위해 사용 가능한 설정 및 사용자가 모바일 장치에서 Office 파일에 액세스하는 방법을 제어하는 설정에 대한 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-128">The following tables give detailed information about the available settings to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="f9fd5-129">자세한 내용은 [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md)(Microsoft 365 Business의 보호 기능을 Intune 설정에 매핑하는 방법)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-129">See [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) for more information.</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="f9fd5-130">작업 파일을 보호하는 설정</span><span class="sxs-lookup"><span data-stu-id="f9fd5-130">Settings that protect work files</span></span>

<span data-ttu-id="f9fd5-131">사용자가 장치를 분실하거나 도난당한 경우 다음과 같은 설정을 사용하여 작업 파일을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-131">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f9fd5-132">설정</span><span class="sxs-lookup"><span data-stu-id="f9fd5-132">Setting</span></span>  <br/> |<span data-ttu-id="f9fd5-133">설명</span><span class="sxs-lookup"><span data-stu-id="f9fd5-133">Description</span></span>  <br/> |
|<span data-ttu-id="f9fd5-134">이 기간이 지난 후 비활성 장치에서 작업 파일 삭제</span><span class="sxs-lookup"><span data-stu-id="f9fd5-134">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="f9fd5-135">여기에 지정한 기간만큼 장치가 사용되지 않는 경우 장치에 저장된 모든 작업 파일이 자동으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-135">If a device is not used for the number of days that you specify here, any work files stored on the device will automatically be deleted.</span></span>  <br/> |
|<span data-ttu-id="f9fd5-136">사용자가 모든 작업 파일을 비즈니스용 OneDrive에 저장하도록 강제 적용</span><span class="sxs-lookup"><span data-stu-id="f9fd5-136">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="f9fd5-137">이 설정이 **켜기**로 되어 있으면 작업 파일은 오직 비즈니스용 OneDrive에만 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-137">If this setting is **On**, the only available save location for work files will be OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="f9fd5-138">작업 파일 암호화</span><span class="sxs-lookup"><span data-stu-id="f9fd5-138">Encrypt work files</span></span>  <br/> |<span data-ttu-id="f9fd5-p104">작업 파일이 암호화로 보호되도록 이 설정을 **켜기**로 둡니다. 장치를 분실하거나 도난당하더라도 다른 사람이 회사 데이터를 읽을 수 없게 됩니다.  </span><span class="sxs-lookup"><span data-stu-id="f9fd5-p104">Keep this setting **On** so that work files are protected by encryption. Even if the device is lost or stolen, no one will be able to read your company data.  </span></span><br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="f9fd5-141">사용자가 모바일 장치에서 Office 파일에 액세스하는 방법을 제어하는 설정</span><span class="sxs-lookup"><span data-stu-id="f9fd5-141">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="f9fd5-142">사용자가 Office 작업 파일을 액세스하는 방법을 관리할 때 다음과 같은 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-142">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f9fd5-143">설정</span><span class="sxs-lookup"><span data-stu-id="f9fd5-143">Setting</span></span>  <br/> |<span data-ttu-id="f9fd5-144">설명</span><span class="sxs-lookup"><span data-stu-id="f9fd5-144">Description</span></span>  <br/> |
|<span data-ttu-id="f9fd5-145">Office 앱 액세스에 PIN 또는 지문 필요</span><span class="sxs-lookup"><span data-stu-id="f9fd5-145">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="f9fd5-146">이 설정이 **켜기**로 되어 있으면 사용자는 사용자 이름 및 암호 외에도 또 다른 형태의 인증을 제공해야 모바일 장치에서 Office 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-146">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="f9fd5-147">PIN을 재설정할 로그인 실패 횟수</span><span class="sxs-lookup"><span data-stu-id="f9fd5-147">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="f9fd5-148">권한 없는 사용자가 PIN을 임의로 추측하는 것을 방지하기 위해 사용자가 지정한 횟수만큼 잘못된 PIN이 입력되면 PIN을 재설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-148">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="f9fd5-149">Office 앱이 이 시간 동안 유휴 상태인 경우 사용자 다시 로그인 필요</span><span class="sxs-lookup"><span data-stu-id="f9fd5-149">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="f9fd5-150">사용자가 얼마 동안 유휴 상태이면 다시 로그인해야 하는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-150">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="f9fd5-151">탈옥 또는 루팅된 장치에서의 작업 파일 액세스 거부</span><span class="sxs-lookup"><span data-stu-id="f9fd5-151">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="f9fd5-p105">기술을 잘 아는 사용자들은 장치를 탈옥 또는 루팅하여 사용할 수 있습니다. 즉, 사용자가 운영 체제를 수정할 수 있기 때문에 장치가 맬웨어에 노출될 확률이 높아집니다. 이 설정이 **켜기** 로 되어 있을 경우 이러한 장치는 차단됩니다.  </span><span class="sxs-lookup"><span data-stu-id="f9fd5-p105">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="f9fd5-155">사용자가 Office 앱의 콘텐츠를 개인 앱으로 복사할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="f9fd5-155">Allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="f9fd5-p106">기본적으로 허용지 않습니다는 있지만 설정에 \*\*\*\* 있으면 사용자 수 복사 정보 작업 파일에 개인 파일을 합니다. 이 설정이 이면 **해제**하는 경우 사용자 개인 응용 프로그램 또는 개인 계정으로 작업 계정에서 정보를 복사할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-p106">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file. If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.  </span></span><br/> |
   

  

