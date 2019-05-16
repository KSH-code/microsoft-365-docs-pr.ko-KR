---
title: 사용자가 모바일 장치에서 Office 문서에 액세스하는 방법 관리
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4OfficeMobile
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
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
description: 모바일 장치에서 Office 앱에 안전 하 게 액세스할 수 있도록 하는 보호 정책에 대해 알아봅니다.
ms.openlocfilehash: cade979635dd5d4a618537d544a7a76ef64a2963
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34071533"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="2f45f-103">사용자가 모바일 장치에서 Office 문서에 액세스하는 방법 관리</span><span class="sxs-lookup"><span data-stu-id="2f45f-103">Manage how users access Office documents on mobile devices</span></span>

 <span data-ttu-id="2f45f-p101">사용자가 모바일 장치에서 Office 파일을 액세스하는 방법을 제어하는 정책 설정은 기본적으로 **꺼짐**으로 되어 있습니다. 설치 중에 기본값을 그대로 수락하여 모든 사용자에게 적용되도록 Android, iOS 및 Windows 10 응용 프로그램 정책을 생성하는 것이 권장됩니다. 설치가 완료되면 추가로 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f45f-p101">Policy settings that control how users access Office files from their mobile devices are **Off** by default. We recommend you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users. You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="2f45f-107">사용자가 모바일 장치에서 Office 파일을 액세스하는 방법을 제어하는 설정</span><span class="sxs-lookup"><span data-stu-id="2f45f-107">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="2f45f-108">사용자가 Office 작업 파일을 액세스하는 방법을 관리할 때 다음과 같은 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f45f-108">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2f45f-109">설정</span><span class="sxs-lookup"><span data-stu-id="2f45f-109">Setting</span></span>  <br/> |<span data-ttu-id="2f45f-110">설명</span><span class="sxs-lookup"><span data-stu-id="2f45f-110">Description</span></span>  <br/> |
|<span data-ttu-id="2f45f-111">Office 앱 액세스에 PIN 또는 지문 필요</span><span class="sxs-lookup"><span data-stu-id="2f45f-111">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="2f45f-112">이 설정이 **켜기**로 되어 있으면 사용자는 사용자 이름 및 암호 외에도 또 다른 형태의 인증을 제공해야 모바일 장치에서 Office 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f45f-112">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="2f45f-113">PIN을 재설정할 로그인 실패 횟수</span><span class="sxs-lookup"><span data-stu-id="2f45f-113">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="2f45f-114">권한 없는 사용자가 PIN을 임의로 추측하는 것을 방지하기 위해 사용자가 지정한 횟수만큼 잘못된 PIN이 입력되면 PIN을 재설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f45f-114">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="2f45f-115">Office 앱이 이 시간 동안 유휴 상태인 경우 사용자 다시 로그인 필요</span><span class="sxs-lookup"><span data-stu-id="2f45f-115">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="2f45f-116">사용자가 얼마 동안 유휴 상태이면 다시 로그인해야 하는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f45f-116">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="2f45f-117">탈옥 또는 루팅된 장치에서의 작업 파일 액세스 거부</span><span class="sxs-lookup"><span data-stu-id="2f45f-117">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="2f45f-p102">기술을 잘 아는 사용자들은 장치를 탈옥 또는 루팅하여 사용할 수 있습니다. 즉, 사용자가 운영 체제를 수정할 수 있기 때문에 장치가 맬웨어에 노출될 확률이 높아집니다. 이 설정이 **켜기** 로 되어 있을 경우 이러한 장치는 차단됩니다.  </span><span class="sxs-lookup"><span data-stu-id="2f45f-p102">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="2f45f-121">사용자가 Office 앱에서 개인 앱으로 콘텐츠를 복사 하도록 허용 하지 않음</span><span class="sxs-lookup"><span data-stu-id="2f45f-121">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="2f45f-122">설정이 설정 되어 있으면 \*\*\*\* 사용자가 작업 파일의 정보를 개인 파일로 복사할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f45f-122">When the setting is **On**, the user can't copy information in a work file to a personal file.</span></span> <span data-ttu-id="2f45f-123">설정이 **해제**되어 있으면 사용자가 작업 파일의 정보를 개인 앱 또는 개인 계정으로 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f45f-123">If the setting is **Off**, the user can copy information from a work file to a personal app or personal account.</span></span>  <br/> |
   

