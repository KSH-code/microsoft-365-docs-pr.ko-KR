---
title: 사용자가 모바일 장치에서 Office 문서에 액세스하는 방법 관리
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- 'O365E_BCSSetup4OfficeMobile '
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: 모바일 장치에서 Office 응용 프로그램에 대 한 보안 액세스 도움이 되는 보호 정책에 알아봅니다.
ms.openlocfilehash: 75dbe79acccabd851c43259a165e79bfe3c509c0
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870034"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="012a3-103">사용자가 모바일 장치에서 Office 문서에 액세스하는 방법 관리</span><span class="sxs-lookup"><span data-stu-id="012a3-103">Manage how users access Office documents on mobile devices</span></span>

 <span data-ttu-id="012a3-p101">사용자가 모바일 장치에서 Office 파일을 액세스하는 방법을 제어하는 정책 설정은 기본적으로 **꺼짐**으로 되어 있습니다. 설치 중에 기본값을 그대로 수락하여 모든 사용자에게 적용되도록 Android, iOS 및 Windows 10 응용 프로그램 정책을 생성하는 것이 권장됩니다. 설치가 완료되면 추가로 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="012a3-p101">Policy settings that control how users access Office files from their mobile devices are **Off** by default. We recommend you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users. You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="012a3-107">사용자가 모바일 장치에서 Office 파일을 액세스하는 방법을 제어하는 설정</span><span class="sxs-lookup"><span data-stu-id="012a3-107">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="012a3-108">사용자가 Office 업무 파일에 액세스하는 방법을 관리할 때 다음과 같은 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="012a3-108">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="012a3-109">설정</span><span class="sxs-lookup"><span data-stu-id="012a3-109">Setting</span></span>  <br/> |<span data-ttu-id="012a3-110">설명</span><span class="sxs-lookup"><span data-stu-id="012a3-110">Description</span></span>  <br/> |
|<span data-ttu-id="012a3-111">Office 앱 액세스에 PIN 또는 지문 필요</span><span class="sxs-lookup"><span data-stu-id="012a3-111">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="012a3-112">이 설정이 **켜짐**으로 되어 있으면 사용자는 사용자 이름 및 암호 외에 다른 인증 수단을 제공해야 모바일 장치에서 Office 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="012a3-112">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="012a3-113">이 횟수만큼 로그인 실패 시 PIN 재설정</span><span class="sxs-lookup"><span data-stu-id="012a3-113">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="012a3-114">권한 없는 사용자가 PIN을 임의로 추측하는 것을 방지하기 위해 사용자가 지정한 횟수만큼 잘못된 PIN이 입력되면 PIN을 재설정합니다.</span><span class="sxs-lookup"><span data-stu-id="012a3-114">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="012a3-115">Office 앱이 이 시간 동안 유휴 상태인 경우 사용자 다시 로그인 필요</span><span class="sxs-lookup"><span data-stu-id="012a3-115">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="012a3-116">사용자가 얼마 동안 유휴 상태이면 다시 로그인해야 하는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="012a3-116">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="012a3-117">탈옥 또는 루팅된 장치에서의 작업 파일 액세스 거부</span><span class="sxs-lookup"><span data-stu-id="012a3-117">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="012a3-p102">기술을 잘 아는 사용자들은 장치를 탈옥 또는 루팅하여 사용할 수 있습니다. 즉, 사용자가 운영 체제를 수정할 수 있기 때문에 장치가 맬웨어에 노출될 확률이 높아집니다. 이 설정이 **켜짐**으로 되어 있을 경우 이러한 장치는 차단됩니다.  </span><span class="sxs-lookup"><span data-stu-id="012a3-p102">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="012a3-121">사용자가 Office 앱의 콘텐츠를 개인 앱으로 복사할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="012a3-121">Allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="012a3-p103">기본적으로 허용되는 설정입니다. 이 설정이 **켜짐**으로 되어 있으면 사용자가 업무 파일의 정보를 개인 파일로 복사할 수 있습니다. 이 설정이 **꺼짐**으로 되어 있으면 사용자가 업무 파일의 정보를 개인 앱 또는 개인 계정으로 복사할 수 없습니다.  </span><span class="sxs-lookup"><span data-stu-id="012a3-p103">We allow this by default, but when the setting is **On**, the user can copy information in a work file to a personal file. If the setting is **Off**, the user can't copy information from a work file to a personal app or personal account.  </span></span><br/> |
   

