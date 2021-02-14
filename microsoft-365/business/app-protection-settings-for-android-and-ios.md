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
description: 앱 관리 정책을 작성, 편집 또는 삭제하고 Android 또는 iOS 장치에서 작업 파일을 보호하는 방법을 자세히 알아보는 방법을 배워보아야 합니다.
ms.openlocfilehash: 67e7aaec5ff5a28f1e2d489913246c1c15c2f7b6
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2020
ms.locfileid: "44471202"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="828ca-103">Android 또는 iOS 장치에서 앱 보호 설정 설정하기</span><span class="sxs-lookup"><span data-stu-id="828ca-103">Set app protection settings for Android or iOS devices</span></span>

<span data-ttu-id="828ca-104">이 문서는 Microsoft 365 Business Premium에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="828ca-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="create-an-app-management-policy"></a><span data-ttu-id="828ca-105">앱 관리 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="828ca-105">Create an app management policy</span></span>

1. <span data-ttu-id="828ca-106"><a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="828ca-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="828ca-107">In the left nav, choose **Devices** \> **Policies** \> **Add**.</span><span class="sxs-lookup"><span data-stu-id="828ca-107">In the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="828ca-108">**정책 추가** 창에서 이 정책의 고유 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="828ca-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="828ca-109">정책 **유형에서** 만들 정책 집합에 따라 **Android용** 응용 프로그램 관리 또는 **iOS용** 응용 프로그램 관리를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="828ca-109">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS**, depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="828ca-110">장치를 **분실하거나** 도난당한 경우 작업 파일 보호를 확장하고 사용자가 모바일 장치에서 Office 파일에 액세스하는 방법을 **관리합니다.**</span><span class="sxs-lookup"><span data-stu-id="828ca-110">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices**.</span></span> <span data-ttu-id="828ca-111">원하는 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="828ca-111">Configure the settings how you would like.</span></span> <span data-ttu-id="828ca-112">**사용자가 모바일 장치에서 Office 파일에**  액세스하는 방법을 관리하면 기본적으로 꺼지지만 켜고 기본값을 수락하는 것이 좋습니다. </span><span class="sxs-lookup"><span data-stu-id="828ca-112">**Manage how users access Office files on mobile devices** is **Off** by default, but we recommend that you turn it **On** and accept the default values.</span></span> <span data-ttu-id="828ca-113">자세한 내용은 사용 가능한 설정을 [참조하세요.](#available-settings)</span><span class="sxs-lookup"><span data-stu-id="828ca-113">For more information, see [Available settings](#available-settings).</span></span> 
    
    <span data-ttu-id="828ca-114">언제든지 **기본 설정 다시 설정** 링크를 사용하여 기본 설정으로 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="828ca-114">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](../media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="828ca-116">Next decide **Who will get these settings?**</span><span class="sxs-lookup"><span data-stu-id="828ca-116">Next decide **Who will get these settings?**</span></span> <span data-ttu-id="828ca-117">기본 모든 사용자 보안 그룹을  사용하지 않는 경우 변경을 선택하고 **이러한** 설정을 사용하는 보안 그룹을 \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="828ca-117">If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups that get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="828ca-118">마지막으로 **완료** 를 선택하여 정책을 저장하고 장치를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="828ca-118">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="828ca-119">앱 관리 정책 편집</span><span class="sxs-lookup"><span data-stu-id="828ca-119">Edit an app management policy</span></span>

1. <span data-ttu-id="828ca-120">정책 **카드에서** 정책 **편집을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="828ca-120">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="828ca-121">**정책 편집** 창에서 변경하려는 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="828ca-121">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="828ca-122">정책에서 값을 변경하려는 각 설정 옆의 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="828ca-122">Choose **Edit** next to each setting to change the values in the policy.</span></span> <span data-ttu-id="828ca-123">값을 변경하면 정책에 자동으로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="828ca-123">When you change a value, it's automatically saved in the policy.</span></span>
    
4. <span data-ttu-id="828ca-124">완료되면 정책 편집 **창을 닫습니다.**</span><span class="sxs-lookup"><span data-stu-id="828ca-124">When you're finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="828ca-125">앱 관리 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="828ca-125">Delete an app management policy</span></span>

1. <span data-ttu-id="828ca-126">정책 **페이지에서** 정책을 선택한 다음 **삭제합니다.**</span><span class="sxs-lookup"><span data-stu-id="828ca-126">On the **Policies** page, choose a policy and then **Delete**.</span></span>
    
2. <span data-ttu-id="828ca-127">정책 삭제 **창에서** **선택한** 정책 또는 정책을 삭제하려면 확인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="828ca-127">On the **Delete policy** pane, choose **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="828ca-128">사용 가능한 설정</span><span class="sxs-lookup"><span data-stu-id="828ca-128">Available settings</span></span>

<span data-ttu-id="828ca-129">다음 표에서는 장치에서 작업 파일을 보호하는 데 사용할 수 있는 설정과 사용자가 모바일 장치에서 Office 파일에 액세스하는 방법을 제어하는 설정에 대한 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="828ca-129">The following tables give detailed information about settings available to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="828ca-130">자세한 내용은 [Microsoft 365 Business Premium의](map-protection-features-to-intune-settings.md)보호 기능을 Intune 설정에 매핑하는 방법을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="828ca-130">For more information, see [How do protection features in Microsoft 365 Business Premium map to Intune settings](map-protection-features-to-intune-settings.md).</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="828ca-131">업무 파일을 보호하는 설정</span><span class="sxs-lookup"><span data-stu-id="828ca-131">Settings that protect work files</span></span>

<span data-ttu-id="828ca-132">사용자가 장치를 분실하거나 도난당한 경우 다음과 같은 설정을 사용하여 업무 파일을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="828ca-132">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="828ca-133">설정</span><span class="sxs-lookup"><span data-stu-id="828ca-133">Setting</span></span>  <br/> |<span data-ttu-id="828ca-134">설명</span><span class="sxs-lookup"><span data-stu-id="828ca-134">Description</span></span>  <br/> |
|<span data-ttu-id="828ca-135">이 기간이 지난 후 비활성 장치에서 업무 파일 삭제</span><span class="sxs-lookup"><span data-stu-id="828ca-135">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="828ca-136">여기서 지정한 일 수 동안 디바이스를 사용하지 않으면 장치에 저장된 모든 작업 파일이 자동으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="828ca-136">If a device isn't used for the number of days that you specify here, any work files stored on the device will be deleted automatically.</span></span>  <br/> |
|<span data-ttu-id="828ca-137">사용자가 모든 업무 파일을 비즈니스용 OneDrive에 저장하도록 강제 적용</span><span class="sxs-lookup"><span data-stu-id="828ca-137">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="828ca-138">이 설정이 **On인** 경우 작업 파일에 대해 사용할 수 있는 유일한 저장 위치는 비즈니스용 OneDrive입니다.</span><span class="sxs-lookup"><span data-stu-id="828ca-138">If this setting is **On**, the only available save location for work files is OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="828ca-139">업무 파일 암호화</span><span class="sxs-lookup"><span data-stu-id="828ca-139">Encrypt work files</span></span>  <br/> |<span data-ttu-id="828ca-140">업무 파일이 암호화로 보호되도록 이 설정을 **켜짐** 으로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="828ca-140">Keep this setting **On** so that work files are protected by encryption.</span></span> <span data-ttu-id="828ca-141">장치를 분실하거나 도난당한 경우에도 누구도 회사 데이터를 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="828ca-141">Even if the device is lost or stolen, no one can read your company data.</span></span>  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="828ca-142">사용자가 모바일 장치에서 Office 파일에 액세스하는 방법을 제어하는 설정</span><span class="sxs-lookup"><span data-stu-id="828ca-142">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="828ca-143">사용자가 Office 작업 파일을 액세스하는 방법을 관리할 때 다음과 같은 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="828ca-143">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="828ca-144">설정</span><span class="sxs-lookup"><span data-stu-id="828ca-144">Setting</span></span>  <br/> |<span data-ttu-id="828ca-145">설명</span><span class="sxs-lookup"><span data-stu-id="828ca-145">Description</span></span>  <br/> |
|<span data-ttu-id="828ca-146">Office 앱 액세스에 PIN 또는 지문 필요</span><span class="sxs-lookup"><span data-stu-id="828ca-146">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="828ca-147">이 설정이 **On인** 경우 사용자가 모바일 장치에서 Office 앱을 사용하기 전에 사용자 이름 및 암호 외에 다른 인증 형식을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="828ca-147">If this setting is **On** users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile devices.</span></span><br/> |
|<span data-ttu-id="828ca-148">PIN을 재설정할 로그인 실패 횟수</span><span class="sxs-lookup"><span data-stu-id="828ca-148">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="828ca-149">권한 없는 사용자가 PIN을 임의로 추측하는 것을 방지하기 위해 사용자가 지정한 횟수만큼 잘못된 PIN이 입력되면 PIN을 재설정합니다.</span><span class="sxs-lookup"><span data-stu-id="828ca-149">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="828ca-150">Office 앱이 이 시간 동안 유휴 상태인 경우 사용자 다시 로그인 필요</span><span class="sxs-lookup"><span data-stu-id="828ca-150">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="828ca-151">이 설정은 사용자에게 다시 로그인하라는 메시지가 표시되기 전에 유휴 시간이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="828ca-151">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="828ca-152">탈옥 또는 루팅된 장치에서의 작업 파일 액세스 거부</span><span class="sxs-lookup"><span data-stu-id="828ca-152">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="828ca-p105">기술을 잘 아는 사용자들은 장치를 탈옥 또는 루팅하여 사용할 수 있습니다. 즉, 사용자가 운영 체제를 수정할 수 있기 때문에 장치가 맬웨어에 노출될 확률이 높아집니다. 이 설정이 **켜기** 로 되어 있을 경우 이러한 장치는 차단됩니다.  </span><span class="sxs-lookup"><span data-stu-id="828ca-p105">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="828ca-156">사용자가 Office 앱에서 개인 앱으로 콘텐츠를 복사하도록 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="828ca-156">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="828ca-157">기본적으로 허용되는 설정이지만 이 설정이 **켜기** 로 되어 있을 경우 사용자가 작업 파일의 정보를 개인 파일로 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="828ca-157">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file.</span></span> <span data-ttu-id="828ca-158">이 설정이 **끄기** 로 되어 있으면 사용자가 회사 계정의 정보를 개인 앱 또는 개인 계정으로 복사할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="828ca-158">If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.</span></span>  <br/> |
