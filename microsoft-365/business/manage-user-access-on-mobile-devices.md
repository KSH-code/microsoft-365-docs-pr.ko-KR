---
title: 사용자가 모바일 장치에서 Office 문서에 액세스하는 방법 관리
f1.keywords:
- NOCSH
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
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: 사용자가 모바일 장치에서 Office 앱 및 작업 파일에 액세스 하는 방법을 관리 하는 데 사용할 수 있는 보호 정책에 대해 알아봅니다.
ms.openlocfilehash: 870706103a6c05e2e193c80f7a586eab529bb1e7
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42561503"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="b203e-103">사용자가 모바일 장치에서 Office 문서에 액세스하는 방법 관리</span><span class="sxs-lookup"><span data-stu-id="b203e-103">Manage how users access Office documents on mobile devices</span></span>

 <span data-ttu-id="b203e-104">사용자가 모바일 장치에서 Office 파일을 액세스하는 방법을 제어하는 정책 설정은 기본적으로 **꺼짐**으로 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b203e-104">Policy settings that control how users access Office files from their mobile devices are **Off** by default.</span></span> <span data-ttu-id="b203e-105">설치 중에 기본값을 사용 하 여 모든 사용자에 게 적용 되는 Android, iOS 및 Windows 10에 대 한 응용 프로그램 정책을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b203e-105">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="b203e-106">설치가 완료되면 추가로 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b203e-106">You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="b203e-107">사용자가 모바일 장치에서 Office 파일을 액세스하는 방법을 제어하는 설정</span><span class="sxs-lookup"><span data-stu-id="b203e-107">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="b203e-108">사용자가 Office 작업 파일을 액세스하는 방법을 관리할 때 다음과 같은 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b203e-108">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b203e-109">설정</span><span class="sxs-lookup"><span data-stu-id="b203e-109">Setting</span></span>  <br/> |<span data-ttu-id="b203e-110">설명</span><span class="sxs-lookup"><span data-stu-id="b203e-110">Description</span></span>  <br/> |
|<span data-ttu-id="b203e-111">Office 앱 액세스에 PIN 또는 지문 필요</span><span class="sxs-lookup"><span data-stu-id="b203e-111">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="b203e-112">이 설정이 설정 되어 있으면 사용자가 모바일 장치에서 Office **앱을 사용**하기 전에 다른 인증 형식 (사용자 이름 및 암호 추가)을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b203e-112">If this setting is **On**, users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="b203e-113">PIN을 재설정할 로그인 실패 횟수</span><span class="sxs-lookup"><span data-stu-id="b203e-113">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="b203e-114">권한 없는 사용자가 PIN을 임의로 추측하는 것을 방지하기 위해 사용자가 지정한 횟수만큼 잘못된 PIN이 입력되면 PIN을 재설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b203e-114">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="b203e-115">Office 앱이 이 시간 동안 유휴 상태인 경우 사용자 다시 로그인 필요</span><span class="sxs-lookup"><span data-stu-id="b203e-115">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="b203e-116">이 설정은 사용자가 다시 로그인 하 라는 메시지가 표시 될 때까지 유휴 상태일 수 있는 기간을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b203e-116">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="b203e-117">탈옥 또는 루팅된 장치에서의 작업 파일 액세스 거부</span><span class="sxs-lookup"><span data-stu-id="b203e-117">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="b203e-118">기술을 잘 아는 사용자들은 장치를 탈옥 또는 루팅하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b203e-118">Clever users may have a device that is jailbroken or rooted.</span></span> <span data-ttu-id="b203e-119">즉, 사용자가 운영 체제를 수정할 수 있기 때문에 장치가 맬웨어에 취약 해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b203e-119">This means that the user can modify the operating system, which can make the device more susceptible to malware.</span></span> <span data-ttu-id="b203e-120">이 설정이 **켜기** 로 되어 있을 경우 이러한 장치는 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="b203e-120">These devices are blocked when this setting is **On**.</span></span>  <br/> |
|<span data-ttu-id="b203e-121">사용자가 Office 앱에서 개인 앱으로 콘텐츠를 복사 하도록 허용 하지 않음</span><span class="sxs-lookup"><span data-stu-id="b203e-121">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="b203e-122">설정이 설정 되어 있으면 사용자가 작업 파일의 **정보를 개인**파일로 복사할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b203e-122">When the setting is **On**, the user can't copy information in a work file to a personal file.</span></span> <span data-ttu-id="b203e-123">설정이 **해제**되어 있으면 사용자가 작업 파일의 정보를 개인 앱 또는 개인 계정으로 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b203e-123">If the setting is **Off**, the user can copy information from a work file to a personal app or personal account.</span></span>  <br/> |
   

