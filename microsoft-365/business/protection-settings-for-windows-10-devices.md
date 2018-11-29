---
title: Windows 10 장치에서 응용 프로그램 보호 설정 설정하기
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: 응용 프로그램 관리 정책 만들기 및 Windows 10 장치에서 작업 파일을 보호 하는 방법에 알아봅니다.
ms.openlocfilehash: acf19a72d994185a35b2e425f8334a73a121ee10
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869921"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="1a9f5-103">Windows 10 장치에서 응용 프로그램 보호 설정 설정하기</span><span class="sxs-lookup"><span data-stu-id="1a9f5-103">Set application protection settings for Windows 10 devices</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="1a9f5-104">Windows 10용 앱 관리 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="1a9f5-104">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="1a9f5-105">사용자들이 업무를 수행할 수 있는 개인 Windows 10 장치를 갖고 있는 경우, 해당 장치에서도 데이터를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a9f5-105">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="1a9f5-p101">전역 관리자 자격 증명을 사용하여 [Microsoft 365 Business](https://portal.office.com)에 로그인합니다. **관리** 타일을 선택하여 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1a9f5-p101">Sign in to [Microsoft 365 Business](https://portal.office.com) with global admin credentials. Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="1a9f5-108">관리 포털의 **장치 정책** 카드에서 **정책 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1a9f5-108">On the **Device policies** card of the admin portal, choose **Add policy**.</span></span>
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. <span data-ttu-id="1a9f5-110">**정책 추가** 창에서 이 정책의 고유 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1a9f5-110">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="1a9f5-111">**정책 유형**에서 **Windows 10용 응용 프로그램 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1a9f5-111">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
    
5. <span data-ttu-id="1a9f5-112">아래에서 \* \* 장치 유형 \* \*, **개인** 또는 **회사 소유 하 고**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a9f5-112">Under \*\* Device type \*\*, choose either **Personal** or **Company Owned**.</span></span>
    
6. <span data-ttu-id="1a9f5-113">**작업 파일 암호화**가 자동으로 켜집니다.</span><span class="sxs-lookup"><span data-stu-id="1a9f5-113">The **Encrypt work files** is turned on automatically.</span></span> 
    
7. <span data-ttu-id="1a9f5-114">사용자가 작업 파일을 개인 PC에 저장하지 않도록 하려면 **사용자가 회사 데이터를 개인 파일로 복사하는 것을 차단하고 회사 파일은 비즈니스용 OneDrive에 저장하도록 합니다.** 를 **켜기**로 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="1a9f5-114">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
    
8. <span data-ttu-id="1a9f5-p102">**사용자가 장치에서 Office 파일을 액세스 하는 방식을 관리할** 확장 하 고 \> 하려는 방식 설정을 구성 합니다. 기본적으로 **해제** 되어 **사용자가 모바일 장치에서 Office 장치를 액세스 하는 방식을 관리** 하지만 **에** 설정 하 고 기본값을 적용 하는 것이 좋습니다. 자세한 내용은 [사용할 수 있는 설정](protection-settings-for-windows-10-devices.md#bkmk_settings) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1a9f5-p102">Expand **Manage how users access Office files on devices** \> configure the settings how you would like. The **Manage how users access Office devices on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values. See [Available settings](protection-settings-for-windows-10-devices.md#bkmk_settings) for more information.</span></span> 
    
    <span data-ttu-id="1a9f5-118">언제든지 **기본 설정 다시 설정** 링크를 사용하여 기본 설정으로 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a9f5-118">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
9. <span data-ttu-id="1a9f5-119">**Windows 장치에서 데이터 복구**를 확장하여 **켜기**로 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1a9f5-119">Expand **Recover data on Windows devices** and it is recommended that you turn it **On**.</span></span>
    
    <span data-ttu-id="1a9f5-p103">데이터 복구 에이전트 인증서의 위치를 찾기 전에 먼저 하나 만들어야 합니다. 지침은 [EFS(파일 시스템 암호화) DRA(데이터 복구 에이전트) 인증서 만들기 및 확인](https://go.microsoft.com/fwlink/p/?linkid=853700)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a9f5-p103">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one. For instructions see, [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="1a9f5-p104">기본적으로 작업 파일은 장치에 저장되고 사용자 프로필과 연결된 비밀 키를 사용하여 암호화됩니다. 사용자만 파일을 열고 암호 해독할 수 있습니다. 그러나 장치를 분실하거나 사용자가 제거된 경우 파일이 암호화된 상태에 계속 머물러 있을 수 있습니다. 관리자가 DRA(데이터 복구 에이전트) 인증서를 사용하여 파일의 암호를 해독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a9f5-p104">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile. Only the user can open and decrypt the file. However, if a device is lost or a user is removed, a file can be stuck in an encrypted state. The Data Recovery Agent (DRA) certificate can be used by an admin to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="1a9f5-p105">추가 도메인 또는 SharePoint Online 위치를 추가하여 나열된 모든 앱이 보호되는지 확인하려면 **Protect additional network and cloud locations**(추가 네트워크 및 클라우드 위치 보호)를 확장합니다. 필드에 2개 이상의 항목을 입력해야 하는 경우 항목 사이에 세미콜론(;)을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="1a9f5-p105">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps will be protected. If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span> 
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="1a9f5-p106">다음으로 **이러한 설정을 적용할 대상은 누구입니까?** 를 설정하세요. **모든 사용자** 기본 보안 그룹을 사용하지 않으려는 경우 **변경**을 선택하고 이 설정을 적용할 보안 그룹 \> **선택**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1a9f5-p106">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
12. <span data-ttu-id="1a9f5-132">마지막으로 **추가**를 선택하여 정책을 저장하고 장치에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="1a9f5-132">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="1a9f5-133">사용 가능한 설정</span><span class="sxs-lookup"><span data-stu-id="1a9f5-133">Available settings</span></span>

<span data-ttu-id="1a9f5-134">사용자가 Office 작업 파일을 액세스하는 방법을 관리할 때 다음과 같은 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a9f5-134">The following settings are available to manage how users access Office work files.</span></span>
  
<span data-ttu-id="1a9f5-135">자세한 내용은 [Microsoft 365 Business의 보호 기능을 Intune 설정에 매핑하는 방법](map-protection-features-to-intune-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a9f5-135">For more information, see [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md).</span></span>
  
|<span data-ttu-id="1a9f5-136">**설정**</span><span class="sxs-lookup"><span data-stu-id="1a9f5-136">**Setting**</span></span>|<span data-ttu-id="1a9f5-137">**설명**</span><span class="sxs-lookup"><span data-stu-id="1a9f5-137">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1a9f5-138">Office 앱 액세스에 PIN 또는 지문 필요</span><span class="sxs-lookup"><span data-stu-id="1a9f5-138">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="1a9f5-139">이 설정이 **켜기**로 되어 있으면 사용자는 사용자 이름 및 암호 외에도 또 다른 형태의 인증을 제공해야 모바일 장치에서 Office 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a9f5-139">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="1a9f5-140">PIN을 재설정할 로그인 실패 횟수</span><span class="sxs-lookup"><span data-stu-id="1a9f5-140">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="1a9f5-141">권한 없는 사용자가 PIN을 임의로 추측하는 것을 방지하기 위해 사용자가 지정한 횟수만큼 잘못된 PIN이 입력되면 PIN을 재설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1a9f5-141">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="1a9f5-142">Office 앱이 이 시간 동안 유휴 상태인 경우 사용자 다시 로그인 필요</span><span class="sxs-lookup"><span data-stu-id="1a9f5-142">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="1a9f5-143">사용자가 얼마 동안 유휴 상태이면 다시 로그인해야 하는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1a9f5-143">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
   

