---
title: Android 또는 iOS 장치에서 앱 보호 설정 설정하기
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
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: 앱 관리 정책을 만들고, 편집 하 고, 삭제 하 고, Android 또는 iOS 장치에서 작업 파일을 보호 하는 방법을 알아봅니다.
ms.openlocfilehash: 2eebe5b603837d7e4125ab7e88b61792ca3a1e5d
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38321848"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="aa475-103">Android 또는 iOS 장치에서 앱 보호 설정 설정하기</span><span class="sxs-lookup"><span data-stu-id="aa475-103">Set app protection settings for Android or iOS devices</span></span>

![를 https://aka.ms/aboutM365preview가리키는 배너입니다.](media/m365admincenterchanging.png)

## <a name="create-an-app-management-policy"></a><span data-ttu-id="aa475-105">앱 관리 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="aa475-105">Create an app management policy</span></span>

1. <span data-ttu-id="aa475-106"><a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="aa475-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="aa475-107">왼쪽 탐색 창에서 **장치** \> **정책** \> **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa475-107">In the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="aa475-108">**정책 추가** 창에서 이 정책의 고유 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="aa475-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="aa475-109">**정책 유형에**서 만들려는 정책 집합에 따라 **Android 용 응용 프로그램 관리** 또는 **iOS 용 응용**프로그램 관리를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa475-109">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS**, depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="aa475-110">**장치를 분실 하거나 도난당 한 경우 작업 파일 보호** 를 확장 하 고 **사용자가 모바일 장치에서 Office 파일에 액세스 하는 방법을 관리**합니다.</span><span class="sxs-lookup"><span data-stu-id="aa475-110">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices**.</span></span> <span data-ttu-id="aa475-111">설정을 구성 하 여 원하는 방식으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa475-111">Configure the settings how you would like.</span></span> <span data-ttu-id="aa475-112">**사용자가 모바일 장치에서 Office 파일에 액세스 하는 방법** 에 대 한 자세한 내용은 기본적으로 **해제** 되어 있지만 설정 **하 고 기본값** 을 그대로 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="aa475-112">**Manage how users access Office files on mobile devices** is **Off** by default, but we recommend that you turn it **On** and accept the default values.</span></span> <span data-ttu-id="aa475-113">자세한 내용은 [사용 가능한 설정을](#available-settings)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aa475-113">For more information, see [Available settings](#available-settings).</span></span> 
    
    <span data-ttu-id="aa475-114">언제든지 **기본 설정 다시 설정** 링크를 사용하여 기본 설정으로 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa475-114">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="aa475-116">Next decide **Who will get these settings?**</span><span class="sxs-lookup"><span data-stu-id="aa475-116">Next decide **Who will get these settings?**</span></span> <span data-ttu-id="aa475-117">기본값인 **모든 사용자** 보안 그룹을 사용 하지 않으려는 경우 **변경을**선택 하 고 이러한 설정이 \> 있는 보안 그룹을 **선택**합니다.</span><span class="sxs-lookup"><span data-stu-id="aa475-117">If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups that get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="aa475-118">마지막으로 **완료**를 선택하여 정책을 저장하고 장치를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="aa475-118">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="aa475-119">앱 관리 정책 편집</span><span class="sxs-lookup"><span data-stu-id="aa475-119">Edit an app management policy</span></span>

1. <span data-ttu-id="aa475-120">**정책** 카드에서 **정책 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa475-120">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="aa475-121">**정책 편집** 창에서 변경하려는 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="aa475-121">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="aa475-122">정책에서 값을 변경하려는 각 설정 옆의 **편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="aa475-122">Choose **Edit** next to each setting to change the values in the policy.</span></span> <span data-ttu-id="aa475-123">값을 변경 하면 정책에 자동으로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa475-123">When you change a value, it's automatically saved in the policy.</span></span>
    
4. <span data-ttu-id="aa475-124">작업이 완료 되 면 **정책 편집** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="aa475-124">When you're finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="aa475-125">앱 관리 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="aa475-125">Delete an app management policy</span></span>

1. <span data-ttu-id="aa475-126">**정책 페이지에서** 정책을 선택 하 고 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa475-126">On the **Policies** page, choose a policy and then **Delete**.</span></span>
    
2. <span data-ttu-id="aa475-127">**정책 삭제** 창에서 **확인** 을 선택 하 여 선택한 정책 또는 정책을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa475-127">On the **Delete policy** pane, choose **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="aa475-128">사용 가능한 설정</span><span class="sxs-lookup"><span data-stu-id="aa475-128">Available settings</span></span>

<span data-ttu-id="aa475-129">다음 표에서는 장치에서 작업 파일을 보호 하는 데 사용할 수 있는 설정 및 사용자가 모바일 장치에서 Office 파일에 액세스 하는 방법을 제어 하는 설정에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa475-129">The following tables give detailed information about settings available to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="aa475-130">자세한 내용은 [Microsoft 365 Business의 보호 기능을 Intune 설정에 매핑하는 방법](map-protection-features-to-intune-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa475-130">For more information, see [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md).</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="aa475-131">업무 파일을 보호하는 설정</span><span class="sxs-lookup"><span data-stu-id="aa475-131">Settings that protect work files</span></span>

<span data-ttu-id="aa475-132">사용자가 장치를 분실하거나 도난당한 경우 다음과 같은 설정을 사용하여 업무 파일을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa475-132">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="aa475-133">설정</span><span class="sxs-lookup"><span data-stu-id="aa475-133">Setting</span></span>  <br/> |<span data-ttu-id="aa475-134">설명</span><span class="sxs-lookup"><span data-stu-id="aa475-134">Description</span></span>  <br/> |
|<span data-ttu-id="aa475-135">이 기간이 지난 후 비활성 장치에서 업무 파일 삭제</span><span class="sxs-lookup"><span data-stu-id="aa475-135">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="aa475-136">여기에서 지정한 일 수 동안 장치가 사용 되지 않으면 장치에 저장 된 모든 작업 파일이 자동으로 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa475-136">If a device isn't used for the number of days that you specify here, any work files stored on the device will be deleted automatically.</span></span>  <br/> |
|<span data-ttu-id="aa475-137">사용자가 모든 업무 파일을 비즈니스용 OneDrive에 저장하도록 강제 적용</span><span class="sxs-lookup"><span data-stu-id="aa475-137">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="aa475-138">이 설정이 **켜져**있는 경우 작업 파일에 대해 사용할 수 있는 유일한 저장 위치는 비즈니스용 OneDrive입니다.</span><span class="sxs-lookup"><span data-stu-id="aa475-138">If this setting is **On**, the only available save location for work files is OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="aa475-139">업무 파일 암호화</span><span class="sxs-lookup"><span data-stu-id="aa475-139">Encrypt work files</span></span>  <br/> |<span data-ttu-id="aa475-140">업무 파일이 암호화로 보호되도록 이 설정을 **켜짐**으로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="aa475-140">Keep this setting **On** so that work files are protected by encryption.</span></span> <span data-ttu-id="aa475-141">장치를 분실 하거나 도난당 한 경우에도 아무도 회사 데이터를 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aa475-141">Even if the device is lost or stolen, no one can read your company data.</span></span>  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="aa475-142">사용자가 모바일 장치에서 Office 파일에 액세스하는 방법을 제어하는 설정</span><span class="sxs-lookup"><span data-stu-id="aa475-142">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="aa475-143">사용자가 Office 작업 파일을 액세스하는 방법을 관리할 때 다음과 같은 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa475-143">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="aa475-144">설정</span><span class="sxs-lookup"><span data-stu-id="aa475-144">Setting</span></span>  <br/> |<span data-ttu-id="aa475-145">설명</span><span class="sxs-lookup"><span data-stu-id="aa475-145">Description</span></span>  <br/> |
|<span data-ttu-id="aa475-146">Office 앱 액세스에 PIN 또는 지문 필요</span><span class="sxs-lookup"><span data-stu-id="aa475-146">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="aa475-147">이 설정이 사용자 **에** 게 제공 되는 경우 모바일 장치에서 Office 앱을 사용 하기 전에 다른 인증 형식 (사용자 이름 및 암호 추가)을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa475-147">If this setting is **On** users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile devices.</span></span><br/> |
|<span data-ttu-id="aa475-148">PIN을 재설정할 로그인 실패 횟수</span><span class="sxs-lookup"><span data-stu-id="aa475-148">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="aa475-149">권한 없는 사용자가 PIN을 임의로 추측하는 것을 방지하기 위해 사용자가 지정한 횟수만큼 잘못된 PIN이 입력되면 PIN을 재설정합니다.</span><span class="sxs-lookup"><span data-stu-id="aa475-149">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="aa475-150">Office 앱이 이 시간 동안 유휴 상태인 경우 사용자 다시 로그인 필요</span><span class="sxs-lookup"><span data-stu-id="aa475-150">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="aa475-151">이 설정은 사용자가 다시 로그인 하 라는 메시지가 표시 될 때까지 유휴 상태일 수 있는 기간을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa475-151">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="aa475-152">탈옥 또는 루팅된 장치에서의 작업 파일 액세스 거부</span><span class="sxs-lookup"><span data-stu-id="aa475-152">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="aa475-p105">기술을 잘 아는 사용자들은 장치를 탈옥 또는 루팅하여 사용할 수 있습니다. 즉, 사용자가 운영 체제를 수정할 수 있기 때문에 장치가 맬웨어에 노출될 확률이 높아집니다. 이 설정이 **켜기** 로 되어 있을 경우 이러한 장치는 차단됩니다.  </span><span class="sxs-lookup"><span data-stu-id="aa475-p105">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="aa475-156">사용자가 Office 앱의 콘텐츠를 개인 앱으로 복사할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="aa475-156">Allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="aa475-157">기본적으로 허용되는 설정이지만 이 설정이 **켜기**로 되어 있을 경우 사용자가 작업 파일의 정보를 개인 파일로 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa475-157">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file.</span></span> <span data-ttu-id="aa475-158">이 설정이 **끄기** 로 되어 있으면 사용자가 회사 계정의 정보를 개인 앱 또는 개인 계정으로 복사할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aa475-158">If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.</span></span>  <br/> |
